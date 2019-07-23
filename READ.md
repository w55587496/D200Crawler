# Crawl_company

從[電子資料查詢作業 - 臺灣證券交易所](http://https://doc.twse.com.tw/server-java/t57sb01 "電子資料查詢作業 - 臺灣證券交易所")抓取公司的股東會年報

- 請先下載[Python](http://https://www.python.org/downloads/ "Python")

- [移至目錄後，建立虛擬環境](http://https://www.itread01.com/content/1541158272.html "移至目錄後，建立虛擬環境")

- 安裝所需套件
pip install -r equipment.txt

- 資料夾內 chromedriver.exe配合Chrome為版本 75.0.3770.142 (正式版本) (64 位元)
	1. log資料夾用來存放crawl_report.csv，內容為檔案下載狀況
	1. save_crawl資料夾用來存放下載下來的年報
- crawl_target.csv 編碼為utf-8，格式參照附件，內容為抓取目標
- 使用jupter notebook開啟
- crawl_company.ipynb為主要程式碼內容

#### 變數
		year = 年分
		以下list目的取其長度當檔案類型個數
			num_of_doc = [] 
			num_of_docx = []
			num_of_nosuch = []
			num_of_nosuch = []
		存放該次抓取檔案的相關資訊
			file_txt_all_list = [] 
#### function
		webpath(公司代號,年分) : 為該公司查詢後頁面網址
		get_F04(webpath) : 
			在查結果找尋年報檔(結尾是f04)
		file_class(年報檔名) : 
			判斷年報類別
		change_page :
			切分頁
		for_file_pdf(年報檔名,統一編號) ：
			當年報為pdf檔執行下載檔案
		for_other_file(公司代號,年報檔名,統一編號,檔案類型編號)：
			當年報為其他檔案類型執行下載檔案(zip,doc,docx)
		while的大迴圈:
			co_id = 公司代號
			toneyeebanhao = 統一編號
			try
				如果有找到年報檔:進行下載
			except 
				記錄各類錯誤
			crawl_report.csv存入時間/公司代號/統一編號/檔案下載情況/python的exception/以及該公司查詢後的網址





