# LLM-Scientific-Graphical-Abstract-Generator 🧑‍💻📊

## Project Overview 📚🔍

**LLM-Scientific-Graphical-Abstract-Generator** is a tool powered by large language models (LLMs) designed to automatically generate **graphical abstracts** for scientific research papers. By analyzing the textual descriptions and data from research articles, this tool can rapidly create graphical abstracts (such as charts, diagrams, or plots) required for scientific publications. The goal is to help researchers streamline the process of creating graphical abstracts, improve the presentation of their research, and save time ⏳💡.

### Key Features ⚡️:
- Utilizes LLM technology to analyze textual descriptions of research papers and automatically generate **graphical abstracts** 📝➡️📈.
- Supports transforming brief text descriptions into full-fledged graphical representations, such as charts and graphs 📊.
- Handles the entire graphical abstract creation process, including chart type selection, data visualization, and rendering 🎨.
- Outputs in **SVG** format, ensuring high-quality and customizable images 🖼️.
- Provides an easy-to-use interface for quick integration into workflows 🚀.

## Project Structure 🗂️

```
LLM-Scientific-Graphical-Abstract-Generator/
│
├── app/                    # Core application code
│   ├── models/             # LLM model processing and graphical generation logic
│   ├── services/           # Data parsing and backend logic
│   ├── templates/          # Frontend UI components and display templates
│   └── utils/              # Utility classes and helper functions
│
├── examples/               # Example data and generated graphical abstracts
├── requirements.txt        # Project dependencies
├── README.md               # Project documentation
└── setup.py                # Installation configuration
```

## Installation 🛠️

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/LLM-Scientific-Graphical-Abstract-Generator.git
   cd LLM-Scientific-Graphical-Abstract-Generator
   ```

2. Create a virtual environment (recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install project dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Dependencies 📦

This project relies on the following key libraries:

- **transformers**: To load and run pre-trained LLM models (e.g., GPT, T5) 🤖.
- **pandas**: For data processing and parsing 🧮.
- **Flask** or **FastAPI**: To build the backend API that handles user requests and returns generated graphical abstracts 🖥️.
- **D3.js** / **Plotly** / **SVG.js**: For rendering and visualizing charts in the frontend 📊📈.

## Usage 🚀

### 1. Start the Backend Service 🏃‍♂️

The project provides a simple API that allows users to send **POST requests** with the description and data for a graphical abstract, and receive the generated graphical abstract in response.

Run the backend:

```bash
python app/main.py
```

By default, the service will start at `http://localhost:5000`.

### 2. Generate Graphical Abstract 🎨

#### Request Example 📥:

Send a **POST** request to the `/generate` endpoint with the following parameters:

- **text_description**: A brief textual description of the graphical abstract ✍️.
- **data**: Raw data (usually in **CSV** or **JSON** format) to be used for generating the graphical abstract 📊.

#### Request Format:

```json
{
  "text_description": "This chart represents the increase in the number of cases over time. The x-axis represents the months, and the y-axis represents the number of cases.",
  "data": [
    {"month": "January", "cases": 50},
    {"month": "February", "cases": 75},
    {"month": "March", "cases": 120}
  ]
}
```

#### Response Example 📬:

A successful request will return the generated graphical abstract (in **SVG** format) along with metadata:

```json
{
  "status": "success",
  "message": "Graphical abstract generated successfully.",
  "svg_code": "<svg xmlns='http://www.w3.org/2000/svg'...></svg>"
}
```

### 3. Customize the Generated Graphical Abstract ✨

You can customize the generated graphical abstract by modifying:

- The **chart type** (e.g., bar chart, line chart, pie chart) 📊.
- The **colors**, **fonts**, **labels**, and other visual elements 🎨.
- The **data format** (CSV, JSON, etc.) 🔄.

### 4. Visualizing the Graphical Abstract 👀

The generated graphical abstract can be displayed using a frontend application (such as on **Hugging Face Spaces** or a **React app**) or simply downloaded as an **SVG** file 🖼️.

## Examples 🧪

In the `examples/` folder, you can find sample data and generated graphical abstracts:

1. **Example 1**: A line chart based on simple time-series data 📅📈.
2. **Example 2**: A bar chart based on categorical data 📊.
3. **Example 3**: A complete graphical abstract with both charts and explanatory text ✏️.

## Contributing 🤝

We welcome contributions! You can participate by:

- Submitting **issues** or **bug reports** 🐞.
- Suggesting new **features** or **improvements** 💡.
- Submitting **Pull Requests** to fix bugs or add new functionality 🔧.

## Contact 📧

- Maintainer: Menghao Guo
- Email: [menghao.guo.319@gmail.com](mailto:menghao.guo.319@gmail.com)

---

### Project Goal 🎯

The goal of this project is to simplify the process of creating high-quality **graphical abstracts** for scientific papers 🧑‍🔬. By leveraging natural language understanding and automated graphical generation, we aim to free researchers from the tedious task of manually creating figures and charts, allowing them to focus more on their data and findings 📈📚.
