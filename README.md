# LLM-Scientific-Graphical-Abstract-Generator 🧑‍💻📊

## Project Overview 📚🔍

**LLM-Scientific-Graphical-Abstract-Generator** is an advanced tool powered by large language models (LLMs) designed to automatically generate **graphical abstracts** for scientific research papers. By analyzing textual descriptions and relevant data from research articles, this tool can create visual summaries, including data-driven charts, diagrams, and visual representations of the research findings. 

The goal is to assist researchers by automating the creation of **graphical abstracts** that are typically used in scientific papers to quickly convey the essence of the research. This tool saves time and enhances the presentation quality of scientific articles 🧑‍🔬💡.

### Key Features ⚡️:
- Utilizes **LLM technology** to analyze and understand textual descriptions of scientific research 📄.
- Automatically generates **graphical abstracts**, which can include a variety of visual components (e.g., charts, diagrams, and flowcharts) 📊🎨.
- Supports data-driven chart creation, transforming input data (CSV, JSON) into informative visual representations 📈.
- Outputs high-quality **SVG** images that are customizable and scalable 🖼️.
- Provides a simple, easy-to-use API for integrating graphical abstract generation into your workflow 🚀.
- Supports integration with cutting-edge **LLMs** like **Claude**, **ChatGPT**, and **DeepSeek** to enhance content understanding 🤖.

---

## Project Structure 🗂️

The project is organized as follows:

```
LLM-Scientific-Graphical-Abstract-Generator/
│
├── app/                    # Core application code
│   ├── models/             # LLM model processing and graphical generation logic
│   ├── services/           # Data parsing, abstraction, and backend logic
│   ├── templates/          # Frontend UI components and display templates
│   └── utils/              # Utility classes and helper functions
│
├── examples/               # Example data and generated graphical abstracts
├── requirements.txt        # Project dependencies
├── README.md               # Project documentation
└── setup.py                # Installation configuration
```

---

## LLM Model Support 🤖

In the **models** folder, we've designed the system to be flexible and modular, allowing you to configure different LLMs for processing textual descriptions and generating graphical abstracts. This allows users to easily switch between the latest models depending on availability and specific use cases.

### Supported Models:

- **Claude**: By Anthropic, known for its strong reasoning and conversational abilities.
- **ChatGPT**: Powered by OpenAI's GPT models, great for generating and understanding text.
- **DeepSeek**: A cutting-edge model focused on research content understanding and summarization.

You can easily configure the model of your choice in the **configuration settings** or through environment variables, making the integration of new models seamless.

### How to Configure LLMs:

1. **Choose Your LLM**: In the configuration file (`config.py` or environment settings), specify the model you want to use:

   ```python
   LLM_MODEL = "Claude"  # Options: "Claude", "ChatGPT", "DeepSeek"
   ```

2. **API Key Setup**: For models like **ChatGPT** or **Claude**, ensure that your API keys are configured correctly:

   ```bash
   export CHATGPT_API_KEY="your-api-key"
   export CLAUDE_API_KEY="your-api-key"
   ```

3. **Switch Models with Ease**: By simply changing the model name or the API key, you can switch between models without needing to change your code logic.

   Example:

   ```python
   # Dynamically load model based on user configuration
   if LLM_MODEL == "Claude":
       model = ClaudeModel(api_key=os.getenv("CLAUDE_API_KEY"))
   elif LLM_MODEL == "ChatGPT":
       model = ChatGPTModel(api_key=os.getenv("CHATGPT_API_KEY"))
   else:
       model = DeepSeekModel(api_key=os.getenv("DEEPEEK_API_KEY"))
   ```

4. **Custom Model Integration**: You can also add support for new models as they become available, simply by implementing a new class or module in the `models` directory.

---

## Installation 🛠️

To get started with the **LLM-Scientific-Graphical-Abstract-Generator**, follow these steps:

1. **Clone this repository**:

   ```bash
   git clone https://github.com/yourusername/LLM-Scientific-Graphical-Abstract-Generator.git
   cd LLM-Scientific-Graphical-Abstract-Generator
   ```

2. **Create a virtual environment** (recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

---

## Dependencies 📦

This project relies on the following libraries:

- **openai**: To load and utilize pre-trained large language models (e.g., ChatGPT, Claude, DeepSeek) 🤖.
- **pandas**: For data manipulation and processing 🧮.
- **Flask** or **FastAPI**: For the backend service that receives requests and returns graphical abstracts 📡.
- **Plotly** / **D3.js** / **SVG.js**: For rendering charts and diagrams 📊.
- **Matplotlib** / **Seaborn** (optional): For more detailed visualizations, particularly for data-driven charts 📈.

---

## Usage 🚀

### 1. **Start the Backend Service** 🏃‍♂️

The project exposes a simple API to accept textual descriptions and data (in CSV/JSON format), and returns a graphical abstract in **SVG** format.

Run the backend service:

```bash
python app/main.py
```

By default, the backend service will run at `http://localhost:5000`.

### 2. **Generate Graphical Abstract** 🎨

#### Request Example 📥:

Send a **POST** request to the `/generate` endpoint with the following parameters:

- **text_description**: A short description of the research study. This is the text that explains the content and intent of the graphical abstract ✍️.
- **data**: The raw data to be visualized. It should be in a structured format (CSV or JSON) 📊.

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

A successful request will return the generated graphical abstract (in SVG format) along with a status message:

```json
{
  "status": "success",
  "message": "Graphical abstract generated successfully.",
  "svg_code": "<svg xmlns='http://www.w3.org/2000/svg'...></svg>"
}
```

### 3. **Customize the Generated Graphical Abstract** ✨

You can customize the generated graphical abstract by:

- Adjusting the **chart type** (e.g., bar chart, line chart, pie chart) 📊.
- Modifying the **colors**, **fonts**, and **labels** to match your preferred style 🎨.
- Changing the **data format** (CSV, JSON, etc.) 🔄.

### 4. **Visualizing the Graphical Abstract** 👀

The generated graphical abstract can be displayed using a frontend application (such as **React**, **Hugging Face Spaces**, or **Jupyter Notebooks**) or simply downloaded as an **SVG** file 🖼️.

---

## Examples 🧪

In the `examples/` folder, you will find example input data and the corresponding generated graphical abstracts:

1. **Example 1**: A line chart based on simple time-series data 📅📈.
2. **Example 2**: A bar chart representing categorical data 📊.
3. **Example 3**: A complete graphical abstract showcasing both charts and explanatory text ✏️.

---

## Contributing 🤝

We welcome contributions! You can participate in the project by:

- Reporting **bugs** or **issues** 🐞.
- Suggesting **new features** or **improvements** 💡.
- Submitting **Pull Requests** to fix issues or add new functionality 🔧.

---

## Contact 📧

- Maintainer: Menghao Guo
- Email: [menghao.guo.319@gmail.com](mailto:menghao.guo.319@gmail.com)

---

### Project Goal 🎯

The goal of this project is to simplify the process of creating **graphical abstracts** for scientific papers. By leveraging **natural language processing** and **automated graphical generation**, this tool allows researchers to quickly generate high-quality, visually appealing summaries of their work 🧑‍🔬.

