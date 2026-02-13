# Mom-and-Baby RAG -- Crawl Data From VinMec

A lightweight pipeline for **crawling maternal & baby healthcare
articles** from VinMec, then preprocessing them for
**Retrieval-Augmented Generation (RAG)** systems such as Qwen, LLaMA, or
custom Vietnamese medical search engines.

------------------------------------------------------------------------

## 🚀 Features

-   **Web crawler** for VinMec (Sản phụ khoa, Nhi khoa)
-   Extracts **title, content, sections, links**
-   Export to CSV for dataset creation
-   Demo notebooks for data processing and deployment
-   Images illustrating the workflow
-   Clean and modular Python scripts

------------------------------------------------------------------------

## 📁 Project Structure

    Mom-and-Baby-RAG-Crawl-Data-from-VinMec
    │
    ├── README.md                     # Main README
    │
    ├── crawl-python/
    │   ├── crawl_link.py             # Crawl all article URLs
    │   └── crawl_new.py              # Crawl content from URLs
    │
    ├── crawled-data/
    │   ├── crawled_content_from_csv.csv
    │   └── vinmec_nhi_phunu_full_pages.csv
    │
    ├── main-notebook/
    │   ├── Flask-Ngrok-Deloyment.ipynb
    │   └── process_data.ipynb
    │
    ├── sample-vinmec-webpages/
    │   ├── sample_baby.html
    │   └── sample_women.html
    │
    └── img/
        ├── crawl.png
        ├── demo_img_bbdc.png
        ├── demo_img_cddbb.png
        ├── demo_topk.png
        └── output_cell_ngrok.png

------------------------------------------------------------------------

## 🧩 How It Works

### **1️⃣ Crawl URLs**

``` bash
python crawl-python/crawl_link.py
```

This script visits VinMec category pages and extracts all article links
into\
`vinmec_nhi_phunu_full_pages.csv`.

------------------------------------------------------------------------

### **2️⃣ Crawl Article Content**

``` bash
python crawl-python/crawl_new.py
```

-   Extract text
-   Clean HTML
-   Generate structured fields
-   Save to `crawled_content_from_csv.csv`

📌 *You can modify XPath / CSS selectors depending on layout changes.*

------------------------------------------------------------------------

### **3️⃣ Process & Build Dataset (Notebook)**

Notebook:

    main-notebook/process_data.ipynb

Includes: - Text normalization\
- Deduplication\
- Removing JS fragments\
- Chunking for RAG\
- Saving final dataset

------------------------------------------------------------------------

### **4️⃣ Deploy Mini API with Flask + Ngrok**

Notebook:

    main-notebook/Flask-Ngrok-Deloyment.ipynb

Used to create: - REST RAG endpoint\
- Quick testing for mobile/web integration

------------------------------------------------------------------------

## 🖼 Demo Images

### 🔍 Crawl Flow

![crawl](img/crawl.png)

### 📊 Top-K Retrieval Example

![demo_topk](img/demo_topk.png)

### 🍼 Baby-domain Example

![bbdc](img/demo_img_bbdc.png)

### 👩‍🍼 Women-domain Example

![cddbb](img/demo_img_cddbb.png)

### 🌐 Ngrok API Cell Output

![ngrok](img/output_cell_ngrok.png)

------------------------------------------------------------------------

## 🛠 Installation

### **Clone the repo**

``` bash
git clone https://github.com/tienquocbao/Mom-and-Baby-RAG-Crawl-Data-from-VinMec
cd Mom-and-Baby-RAG-Crawl-Data-from-VinMec
```

### **Install dependencies**

``` bash
pip install -r requirements.txt
```

(If `requirements.txt` doesn't exist, install essentials:)

``` bash
pip install requests beautifulsoup4 pandas tqdm flask
```

------------------------------------------------------------------------

## 📜 Requirements

-   Python 3.8+
-   requests\
-   beautifulsoup4\
-   pandas\
-   tqdm\
-   flask\
-   ngrok (optional)

------------------------------------------------------------------------

## 🔮 Future Improvements

-   Add Selenium for dynamic pages\
-   Integrate with FAISS / Milvus\
-   Add Qwen2.5 or LLaMA RAG demo\
-   Build real-time search UI\
-   Auto-update data via cron

------------------------------------------------------------------------

## 👨‍💻 Author

**Huỳnh Thanh Duy**\
GitHub: https://github.com/thduy-h

------------------------------------------------------------------------

## 📄 License

MIT License

------------------------------------------------------------------------

Enjoy building healthcare knowledge systems ❤️
