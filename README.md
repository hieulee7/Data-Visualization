# 📊 Scooby-Doo Data Visualization 
![image](https://github.com/user-attachments/assets/8aea681e-c980-4e05-8909-da0f1cce05c3)

This repository contains an **interactive dashboard** built using **Vega-Lite**, visualizing the evolution of **Scooby-Doo** content (TV series, movies, and specials) from **1969 to 2021**. The dashboard explores the relationship between **distribution channels, networks, audience reception (IMDb scores and votes), and production volume**.

## 🚀 Features  

- **Interactive Bubble Plot** 📈 – Analyzes IMDb scores over time, with episode engagement represented by bubble size.  
- **Bar Chart** 📊 – Displays the total number of episodes by network.  
- **Box Plot** 📦 – Shows the distribution of IMDb scores for each network.  
- **Linked Views & Filtering** 🔗 – Users can interactively filter by time range, distribution type, and network.  
- **Colorblind-Friendly Design** 🎨 – Uses an IBM color palette for accessibility.  

## 📂 Repository Structure  

```
📦 Data-Visualization
 ┣ 📜 updated_scoobydoo.csv          # Cleaned dataset with IMDb scores, networks, and more
 ┣ 📜 final_scoobydoo_dashboard.vl.json  # Vega-Lite specification for the dashboard
 ┣ 📜 Design Document - Hieu Le.pdf  # Detailed design considerations and methodology
 ┣ 📜 README.md                      # Project documentation
```

## 🛠️ How to Run the Visualization  

You need **Vega-Lite** to render the visualization. Follow these steps:

### **Option 1: Use the Vega Editor (Recommended)**  

1. Open **[Vega Editor](https://vega.github.io/editor/)**.  
2. Click **Open** → **Load Vega-Lite JSON**.  
3. Copy and paste the contents of **`final_scoobydoo_dashboard.vl.json`** into the editor.  
4. Click **Run** to generate the interactive visualization.  

### **Option 2: Run Locally**  

1. Install **Vega-Lite** and **Vega-Embed**:
   ```sh
   npm install vega vega-lite vega-embed
   ```
2. Create an **HTML file** (`index.html`) and embed the visualization:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
       <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
       <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
   </head>
   <body>
       <div id="vis"></div>
       <script>
           vegaEmbed("#vis", "final_scoobydoo_dashboard.vl.json");
       </script>
   </body>
   </html>
   ```
3. Open `index.html` in a web browser to view the visualization.

## 📜 Dataset  

The dataset is sourced from [TidyTuesday (Week 29, 2021)](https://github.com/rfordatascience/tidytuesday/blob/main/data/2021/2021-07-13/readme.md), containing information on **Scooby-Doo episodes, air dates, networks, IMDb scores, vote counts, and formats**.  

### **Data Processing**  

- **Handled 15 missing IMDb scores** using values retrieved from IMDb instead of median imputation.  
- **Corrected mislabeled Warner Bros. movies** that were incorrectly categorized as TV series.  
- **Engineered a ‘Distribution Type’ feature** to standardize network groupings.  

## 🎨 Design Considerations  

- **Information Hierarchy** – The **bubble plot** is the main focus, with **bar and box plots** providing complementary insights.  
- **Non-linear size encoding** – IMDb vote counts are **binned logarithmically** to prevent small values from being overshadowed.  
- **Linked Filtering** – Users can interactively filter data using **time brushing, distribution type selection, and network filtering**.  

For a full breakdown, see **[Design Document.pdf](Design Document.pdf)**.  

## 🖥️ Built With  

- **Vega-Lite** – Declarative visualization grammar.  
- **JavaScript (Optional)** – Enhancing interactivity beyond Vega-Lite.  

## 📜 License  

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.  

## 🤝 Contributing  

Contributions are welcome! Feel free to fork this repository, open an issue, or submit a pull request.  

## 📧 Contact  

For any questions or collaborations, reach out via GitHub Issues.  

---

Let me know if you need any refinements! 🚀
