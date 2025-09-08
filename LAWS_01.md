


1 artifact file name format: artifact_01_  
Artifact content: must have timestamped. 

3 không được cùng 1 lúc đề xuất 2-3 options for solution. Chỉ được đề xuất 1 optimal option. Nếu có trục trặc, thì phải tìm mọi cách xử lý để tiếp tục với optimal solution.

4 Bắt buộc đọc file phải đọc 100% từng dòng một. 

5 nếu chỉ mới vào conversation chưa đủ 5 message thì phải chờ approval để edit files

6 Phải cho tôi biết confidence level trước khi trả lời. không được dễ dãi với bản thân cho điểm số confidence cao khi mới vào conversation.

7 Nếu có nhiều files phải đọc thì dùng desktop-commander read multiple files. 

8) Nếu đến câu trả lời thứ 30 thì phải cẩn thận không trả lời quá dài.

9) format trả lời: 
#số thứ tự câu trả lời 
Thời gian: (mm:hh)

10) trả lời tiếng việt. 

11) Không cố định port, phải dynamic bằng PortManager MCP Server

12) ===============================
import requests; print(requests.post("https://api.groq.ai/v1/gpt-oss-120b/generate", headers={"Authorization":"Bearer ihave","Content-Type":"application/json"}, json={"prompt":"Enter your prompt","max_tokens":200}).json())

"D:\.ENV\.env" => Key

13) I work alone with AI. so please avoid all documents that can be confusion to AI. 
ALways separate Business and Technical

14) NEVER HAVE PLACEHOLDER. NEVER MOCK. MUST ALWAYS PUT REAL DATA. 