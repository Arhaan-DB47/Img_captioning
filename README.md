# 🖼️ Image Captioning with BLIP & Gradio

> A progressive learning project exploring AI-powered image captioning — from a simple Gradio hello-world to automated web-page image scraping and captioning.

Built as part of **Course 8 – Building Generative AI-Powered Applications with Python** in the [IBM AI Developer Professional Certificate](https://www.coursera.org/professional-certificates/applied-artifical-intelligence-ibm-watson-ai).

---

## 📌 Overview

This project demonstrates how to use the **Salesforce BLIP** (Bootstrapping Language-Image Pre-training) model to automatically generate natural-language captions for images. It progresses through four scripts, each building on the concepts of the previous one:

| # | File | What It Does |
|---|------|-------------|
| 1 | `hello.py` | A starter Gradio app — validates the environment and introduces the Gradio UI framework. |
| 2 | `image_cap.py` | Loads a local image (`lion.jpg`) and generates a caption using the BLIP model. |
| 3 | `image_captioning_app.py` | Wraps the captioning logic in a Gradio web interface so users can upload any image and get a caption. |
| 4 | `automate_url_captioner.py` | Scrapes all images from a web page (IBM's Wikipedia page), captions each one, and saves the results to `captions.txt`. |

---

## 🧠 Model Used

- **Model**: [`Salesforce/blip-image-captioning-base`](https://huggingface.co/Salesforce/blip-image-captioning-base)
- **Architecture**: BLIP (Bootstrapping Language-Image Pre-training) for conditional image captioning
- **Library**: Hugging Face `transformers`

---

## 📂 Project Structure

```
Img_captioning/
├── hello.py                    # Step 1 — Gradio Hello World
├── image_cap.py                # Step 2 — Caption a local image (lion.jpg)
├── lion.jpg                    # Sample image used by image_cap.py
├── image_captioning_app.py     # Step 3 — Gradio web app for image captioning
├── automate_url_captioner.py   # Step 4 — Scrape & caption images from a URL
├── captions.txt                # Output — Generated captions from Step 4
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/Arhaan-DB47/Img_captioning.git
cd Img_captioning

# Install dependencies
pip install gradio transformers torch pillow requests beautifulsoup4 numpy
```

---

## 📖 Scripts — Step by Step

### Step 1: `hello.py` — Gradio Hello World

A minimal Gradio app that takes a name as input and returns a greeting. This validates that the Gradio framework is working correctly.

```bash
python hello.py
```

The app launches on `http://0.0.0.0:7860`.

---

### Step 2: `image_cap.py` — Caption a Local Image

Loads the pretrained BLIP model and processor, opens `lion.jpg`, and generates a caption using the prompt `"the image of"`.

```bash
python image_cap.py
```

**Example output:**
```
the image of a lion laying on the grass
```

---

### Step 3: `image_captioning_app.py` — Gradio Web App

A Gradio-powered web interface that lets users **upload any image** and receive an AI-generated caption. The BLIP model runs inference on the uploaded image and returns a descriptive caption.

```bash
python image_captioning_app.py
```

**Features:**
- Drag-and-drop or click-to-upload image input
- Real-time caption generation
- Clean, simple UI with title and description

---

### Step 4: `automate_url_captioner.py` — Automated URL Image Captioner

The most advanced script — it scrapes **all images** from a given web page (defaults to the [IBM Wikipedia page](https://en.wikipedia.org/wiki/IBM)), downloads each image, generates a caption using BLIP, and writes the results to `captions.txt`.

```bash
python automate_url_captioner.py
```

**Key features:**
- Web scraping with `BeautifulSoup` — supports `src`, `data-src`, and `srcset` attributes
- Automatic URL resolution for relative paths
- Filters out SVGs and very small images (< 200 px²)
- Graceful error handling for corrupt or unsupported image formats
- Outputs structured `URL: caption` pairs to `captions.txt`

**Sample output (`captions.txt`):**
```
https://...IBM_CHQ_-_Oct_2014.jpg: the image of a building
https://...IBM_Electronic_Data_Processing_Machine.jpg: the image of a man working in a computer lab
https://...IBM360-67AtUmichWithMikeAlexander.jpg: the image of a man sitting in a chair
https://...IBM_PC-IMG_7271.png: the image of a computer with a keyboard
...
```

---

## 🛠️ Technologies & Libraries

| Library | Purpose |
|---------|---------|
| [Hugging Face Transformers](https://huggingface.co/docs/transformers) | BLIP model loading and inference |
| [Gradio](https://gradio.app/) | Web UI for interactive demos |
| [Pillow (PIL)](https://python-pillow.org/) | Image loading and conversion |
| [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/) | HTML parsing and image scraping |
| [Requests](https://docs.python-requests.org/) | HTTP requests for web scraping |
| [PyTorch](https://pytorch.org/) | Backend for model inference |

---

## 📜 License

This project was created for educational purposes as part of the IBM AI Developer Professional Certificate on Coursera.

---

## 👤 Author

**Arhaan Khan** — [@Arhaan-DB47](https://github.com/Arhaan-DB47)
