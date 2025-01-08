A Python tool for automated translation of English PDFs or large text files.

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

