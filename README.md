建置 Python 環境
安裝 Python，確保已包含 pip 工具。
創建資料夾
英文 PDF 資料夾：放入需要翻譯的 PDF 文件（例如 englishpdf 資料夾）。
翻譯後資料夾：用於存放翻譯完成的 Word 文件（例如 cn 資料夾，預設為空）。
在 CMD 中安裝必要模組
執行以下命令依次安裝所需的 Python 套件：
C:/Program Files/Python312/python.exe" -m pip install googletrans==4.0.0-rc1
C:/Program Files/Python312/python.exe" -m pip install opencc-python-reimplemented
C:/Program Files/Python312/python.exe" -m pip install python-docx
C:/Program Files/Python312/python.exe" -m pip install pdfplumber
修改程式內路徑(更新程式中以下路徑為你的資料夾位置)
en_pdf_folder = r"你的英文 PDF 資料夾路徑"
cn_word_folder = r"你的翻譯後文檔存放路徑"
執行程式
翻譯完成後，檢查 cn 資料夾中的 Word 文件即可。

運行流程
初始化環境與資料夾
設定英文 PDF 存放資料夾和翻譯後文件的存放資料夾，如果翻譯後的資料夾不存在，程式會自動建立。
初始化翻譯工具
使用 Google 翻譯（googletrans）進行英文到中文的翻譯。
使用 OpenCC (opencc) 將翻譯結果由簡體轉為繁體中文。
逐檔處理 PDF
遍歷 en_pdf_folder 資料夾內的每個 PDF 文件，為每個 PDF 設定對應的翻譯後 Word 文件的存放路徑。
PDF 翻譯到 Word 的完整流程
文本提取：利用 pdfplumber 提取 PDF 文件中的文字內容。
分段處理：將長文本切分成不超過 3000 字元的小段，避免 Google 翻譯的限制。
逐段翻譯：對每段文字進行翻譯，並透過 OpenCC 轉為繁體中文。
合併結果：將翻譯後的所有段落合併為一整篇文字。
保存為 Word 文件：將翻譯完成的文本保存為 Word 文件，並存入 cn_word_folder。
錯誤處理與重試機制
若翻譯過程中出現問題，程式會重試最多 3 次，並在重試間隔等待 2 秒。
若多次嘗試後仍失敗，該段文本將保留原文，程式繼續處理下一段或下一文件。
完成與輸出
翻譯完成後，顯示已成功處理的檔案及其存放路徑。
