---
title: "Blog 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Thông tin bên dưới chỉ nhằm mục đích tham khảo. Vui lòng **không sao chép nguyên văn** cho báo cáo của bạn, kể cả cảnh báo này. Luôn đọc bài viết gốc để có thông tin chính thống.
{{% /notice %}}

# Các mô hình OpenAI Open‑Weight hiện có trên AWS

AWS cam kết mang đến cho bạn những mô hình nền tảng (foundation models – FMs) tiên tiến nhất trong ngành, liên tục mở rộng danh mục để bao gồm các mô hình đột phá từ những nhà đổi mới AI hàng đầu, nhằm giúp bạn luôn tiếp cận các tiến bộ mới nhất để thúc đẩy doanh nghiệp.

---

Hôm nay, tôi vui mừng thông báo về khả năng sử dụng hai mô hình OpenAI mới với open weights trên Amazon Bedrock và Amazon SageMaker JumpStart. Các mô hình OpenAI gpt-oss-120b và gpt-oss-20b được thiết kế cho tác vụ tạo văn bản và suy luận, mang đến cho nhà phát triển và tổ chức thêm lựa chọn để xây dựng ứng dụng AI với quyền kiểm soát hoàn toàn đối với hạ tầng và dữ liệu của mình.

Các mô hình open weight này xuất sắc trong lập trình, phân tích khoa học và suy luận toán học, với hiệu năng tương đương các lựa chọn hàng đầu. Cả hai hỗ trợ cửa sổ ngữ cảnh 128K và cho phép điều chỉnh mức suy luận (thấp/vừa/cao) phù hợp yêu cầu tình huống. Các mô hình hỗ trợ công cụ bên ngoài để tăng cường khả năng và có thể dùng trong quy trình tác tử (agentic workflow), ví dụ với Strands Agents.

Với Amazon Bedrock và Amazon SageMaker JumpStart, AWS cho bạn tự do đổi mới với quyền truy cập hàng trăm FM từ các công ty AI hàng đầu, bao gồm các mô hình open weight của OpenAI. Nhờ danh mục phong phú, bạn có thể ghép đúng khối lượng công việc AI với mô hình phù hợp mỗi lần.

Thông qua Amazon Bedrock, bạn có thể thử nghiệm liền mạch các mô hình khác nhau, kết hợp năng lực và chuyển đổi giữa các nhà cung cấp mà không phải viết lại mã—biến việc lựa chọn mô hình thành lợi thế chiến lược giúp bạn liên tục tiến hoá chiến lược AI khi có đổi mới mới xuất hiện. Các mô hình mới này có sẵn trên Bedrock qua endpoint tương thích OpenAI. Bạn có thể trỏ OpenAI SDK tới endpoint này hoặc dùng Bedrock InvokeModel và Converse API.

Với SageMaker JumpStart, bạn có thể nhanh chóng đánh giá, so sánh và tuỳ biến mô hình cho trường hợp sử dụng của mình. Sau đó, bạn có thể triển khai bản gốc hoặc bản đã tuỳ biến vào sản xuất bằng SageMaker AI console hoặc SageMaker Python SDK.

Hãy cùng xem chúng hoạt động thế nào trong thực tế.

## Bắt đầu với các mô hình OpenAI open weight trong Amazon Bedrock
Trong bảng điều khiển Amazon Bedrock, tôi chọn Model access từ phần Configure and learn của thanh điều hướng. Sau đó, tôi đi đến hai mô hình OpenAI được liệt kê trên trang này và yêu cầu quyền truy cập.

Khi đã có quyền, tôi dùng Chat/Test playground để thử nghiệm và đánh giá mô hình. Tôi chọn OpenAI là danh mục, rồi chọn mô hình gpt-oss-120b.

![1](/images/3-BlogsTranslated/3.1-Blog1/1.png)

Khi đã có quyền, tôi dùng Chat/Test playground để thử nghiệm và đánh giá mô hình. Tôi chọn OpenAI là danh mục, rồi chọn mô hình gpt-oss-120b.

![2](/images/3-BlogsTranslated/3.1-Blog1/2.png)

Với mô hình này, tôi chạy prompt mẫu sau:

Một gia đình có $5.000 để tiết kiệm cho kỳ nghỉ năm sau. Họ có thể gửi tiền vào tài khoản tiết kiệm lãi 2%/năm hoặc chứng chỉ tiền gửi lãi 4%/năm nhưng không thể rút trước kỳ nghỉ. Nếu họ cần $1.000 cho chi phí khẩn cấp trong năm, họ nên chia số tiền giữa hai lựa chọn thế nào để tối đa hoá quỹ kỳ nghỉ?

Prompt này tạo ra đầu ra bao gồm chuỗi suy luận được dùng để cho ra kết quả.

![3](/images/3-BlogsTranslated/3.1-Blog1/3.png)

Tôi có thể dùng các mô hình này với OpenAI SDK bằng cách cấu hình endpoint API (base URL) và dùng Amazon Bedrock API key để xác thực. Ví dụ, tôi đặt các biến môi trường sau để dùng endpoint khu vực US West (Oregon) (us-west-2) và Bedrock API key của tôi:

#### Bash
```bash
export OPENAI_API_KEY="<my-bedrock-api-key>"
export OPENAI_BASE_URL="https://bedrock-runtime.us-west-2.amazonaws.com/openai/v1"
```

Bây giờ tôi gọi mô hình bằng OpenAI Python SDK.

#### Python
```python
from openai import OpenAI

client = OpenAI()

response = client.chat.completions.create( 
    messages=[{ "role": "user", "content": "Tell me the square root of 42 ^ 3" }],
    model="openai.gpt-oss-120b-1:0",
    stream=True
)

for item in response:
    print(item)
```

Tôi lưu mã (file test-openai.py), cài đặt phụ thuộc và chạy tác tử cục bộ:

#### Bash
```bash
pip install openai
python test-openai.py
```

Để xây dựng một tác tử AI, tôi có thể chọn bất kỳ framework nào hỗ trợ Amazon Bedrock API hoặc OpenAI API. Ví dụ, đây là mã khởi đầu cho Strands Agents dùng Amazon Bedrock API:

#### Python
```python
from strands import Agent
from strands.models import BedrockModel
from strands_tools import calculator

bedrock_model = BedrockModel(
    model_id="openai.gpt-oss-120b-1:0",
    region_name="us-west-2"
)

agent = Agent(
    model=bedrock_model,
    tools=[calculator]
)

agent("Tell me the square root of 42 ^ 3")
```

Tôi lưu mã (file test-strands.py), cài đặt phụ thuộc và chạy tác tử cục bộ:

#### Bash
```bash
pip install strands-agents strands-agents-tools
python test-strands.py
```

Khi hài lòng với tác tử, tôi có thể triển khai vào sản xuất bằng các khả năng của Amazon Bedrock AgentCore, gồm môi trường không máy chủ được quản lý hoàn toàn, quản lý bộ nhớ và danh tính.

## Bắt đầu với các mô hình OpenAI open weight trong Amazon SageMaker JumpStart
Trong bảng điều khiển Amazon SageMaker AI, bạn có thể dùng các mô hình OpenAI open weight trong SageMaker Studio. Lần đầu tiên, tôi cần thiết lập miền SageMaker. Có các tuỳ chọn thiết lập cho một người dùng (đơn giản hơn) hoặc cho tổ chức. Với các thử nghiệm này, tôi dùng thiết lập cho một người dùng.

Trong chế độ xem mô hình SageMaker JumpStart, tôi có quyền truy cập mô tả chi tiết của mô hình gpt-oss-120b hoặc gpt-oss-20b.

![4](/images/3-BlogsTranslated/3.1-Blog1/4.png)

Tôi chọn mô hình gpt-oss-20b rồi triển khai mô hình. Ở các bước tiếp theo, tôi chọn loại phiên bản và số lượng phiên bản ban đầu. Sau vài phút, quá trình triển khai tạo một endpoint mà tôi có thể gọi trong SageMaker Studio và bằng bất kỳ AWS SDK nào.

![5](/images/3-BlogsTranslated/3.1-Blog1/5.png)

Để tìm hiểu thêm, truy cập bài “GPT OSS models from OpenAI are now available on SageMaker JumpStart” trên AWS Artificial Intelligence Blog.

## Những điều cần biết
Các mô hình OpenAI open weight mới hiện có trên Amazon Bedrock tại khu vực US West (Oregon), trong khi Amazon SageMaker JumpStart hỗ trợ các mô hình này tại US East (Ohio, N. Virginia) và Châu Á – Thái Bình Dương (Mumbai, Tokyo).

Mỗi mô hình đi kèm khả năng xuất toàn bộ chuỗi suy luận (chain-of-thought), cung cấp cho bạn mức độ quan sát chi tiết về quá trình lập luận của mô hình. Tính minh bạch này đặc biệt hữu ích cho các ứng dụng đòi hỏi mức độ khả kiến và xác thực cao. Các mô hình này cho bạn tự do sửa đổi, thích nghi và tuỳ biến cho nhu cầu cụ thể. Sự linh hoạt cho phép bạn fine-tune theo trường hợp sử dụng, tích hợp vào quy trình hiện có, và thậm chí xây dựng các mô hình chuyên biệt mới cho ngành/lĩnh vực của bạn.

Bảo mật và an toàn được tích hợp vào lõi của các mô hình, với quy trình đánh giá toàn diện và các biện pháp an toàn. Các mô hình giữ khả năng tương thích với tokenizer chuẩn GPT-4.

Cả hai mô hình có thể được sử dụng trong môi trường bạn ưa thích, dù là trải nghiệm không máy chủ của Amazon Bedrock hay năng lực phát triển ML phong phú của SageMaker JumpStart. Để biết thông tin về chi phí, hãy xem trang giá của Amazon Bedrock và Amazon SageMaker AI.

Để tìm hiểu thêm, xem các tham số của mô hình và cách gọi mô hình bằng OpenAI Chat Completions API trong tài liệu Amazon Bedrock.

Bắt đầu ngay hôm nay với các mô hình OpenAI open weight trên AWS trong bảng điều khiển Amazon Bedrock hoặc Amazon SageMaker AI.

– Danilo
