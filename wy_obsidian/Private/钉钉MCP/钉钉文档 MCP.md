

这是**钉钉文档 MCP（Model Context Protocol）**，一个让 AI Agent 能够操作钉钉在线文档的工具集。

## 核心功能

### 📝 文档操作

| 工具                     | 功能                      |
| ---------------------- | ----------------------- |
| `create_document`      | 创建新文档（支持初始 Markdown 内容） |
| `get_document_content` | 获取文档内容（Markdown 格式返回）   |
| `update_document`      | 更新文档（覆盖/追加模式）           |
| `get_document_info`    | 获取文档元信息（标题、类型、权限等）      |

### 🧱 块元素操作

|工具|功能|
|---|---|
|`list_document_blocks`|查询文档一级块元素列表|
|`insert_document_block`|插入块元素（段落、标题、表格、列表等）|
|`update_document_block`|更新块元素|
|`delete_document_block`|删除块元素|

### 📁 文件/文件夹管理

| 工具                 | 功能                    |
| ------------------ | --------------------- |
| `search_documents` | 搜索文档                  |
| `list_nodes`       | 遍历文件夹/知识库下的节点         |
| `create_folder`    | 创建文件夹                 |
| `create_file`      | 创建各类文件（表格、白板、脑图、多维表等） |
![[attachments/Pasted image 20260323180307.png]]
### 📤 文件上传/下载

|工具|功能|
|---|---|
|`get_file_upload_info`|获取上传凭证（第一步）|
|`commit_uploaded_file`|提交已上传文件（第三步）|
|`download_file`|获取下载凭证|

## 支持的块类型

`paragraph`（段落）、`heading`（标题）、`blockquote`（引用）、`callout`（高亮块）、`columns`（分栏）、`orderedList`（有序列表）、`unorderedList`（无序列表）、`table`（表格）、`sheet`（电子表格）、`attachment`（附件）、`slot`（插槽）

---

**简单说**：这个 MCP 让 AI 可以**读写钉钉文档、管理文件夹、上传下载文件**，功能相当完整。URL 中的 key 参数应该是授权凭证，绑定到特定用户的权限。