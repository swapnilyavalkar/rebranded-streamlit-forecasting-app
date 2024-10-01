# rebranded-streamlit-forecasting-app

rebranded-streamlit-forecasting-app

To install and set up **Streamlit Prophet** in your folder `rebranded-streamlit-forecasting-app` using **VS Code** and **WSL**, follow these steps based on the provided documentation:

### **Prerequisites**
1. **Ensure Python 3.7, 3.8, or 3.9 is installed** in your WSL environment.
   You can check the version by running:
   ```bash
   python3 --version
   sudo apt update
   sudo apt install python3.7
   sudo apt install python3.7-venv
   cd /path/to/rebranded-streamlit-forecasting-app
   python3.7 -m venv streamlit_prophet_env
   source streamlit_prophet_env/bin/activate
   pip install -U pip
   pip install streamlit_prophet
   streamlit_prophet deploy dashboard

   ```

2. **Install WSL2** if you haven't already. Refer to this [WSL2 guide](https://docs.microsoft.com/en-us/windows/wsl/) for setting it up on your Windows machine.

---

### **Steps for Installation and Setup**

1. **Open VS Code with WSL**

   Open your folder `rebranded-streamlit-forecasting-app` in VS Code and connect it to your WSL environment.

   In VS Code, ensure the terminal is using WSL (you can switch the terminal by clicking the dropdown next to the terminal tab and selecting WSL).

2. **Create and Navigate to Project Folder**
   
   In your WSL terminal, navigate to the directory `rebranded-streamlit-forecasting-app`:
   ```bash
   cd /path/to/rebranded-streamlit-forecasting-app
   ```

3. **(Optional) Create a Virtual Environment**

   It's recommended to create a virtual environment to avoid dependency conflicts. Choose one of the following methods:

   **Using `conda`**:
   ```bash
   pip install conda
   conda create -n streamlit_prophet python=3.7
   conda activate streamlit_prophet
   ```

   **Using `virtualenv`**:
   ```bash
   pip install virtualenv
   python3.7 -m virtualenv streamlit_prophet --python=python3.7
   source streamlit_prophet/bin/activate
   ```

4. **Install the Package**

   Install the package from PyPI using the following command:
   ```bash
   pip install -U streamlit_prophet
   ```

   Alternatively, you can install it from the GitHub repository's main branch:
   ```bash
   pip install git+https://github.com/artefactory-global/streamlit_prophet.git@main
   ```

5. **Run the App**

   After installing the package, you can launch the Streamlit app using this command:
   ```bash
   streamlit_prophet deploy dashboard
   ```

   This will open the app in your default web browser, allowing you to upload datasets, train, evaluate, and optimize your forecasting models.

6. **Upload a Dataset**

   - Prepare a CSV file with a date column, target column, and optional features.
   - Upload the dataset via the Streamlit UI and follow the guidelines on the app to forecast and optimize.

---

### **Post-Installation (Optional)**

1. **Containerization with Docker**: 
   If you want to containerize the app, follow the instructions provided in the [`DOCKER.md`](https://github.com/artefactory-global/streamlit_prophet/blob/main/DOCKER.md) file.

2. **Contribute or Extend**:
   Feel free to contribute to the project. You can raise issues or make changes as suggested in the [`CONTRIBUTING.md`](https://github.com/artefactory-global/streamlit_prophet/blob/main/CONTRIBUTING.md) file.

By following these steps, you should be able to successfully install and run the Streamlit Prophet app in your `rebranded-streamlit-forecasting-app` folder using VS Code and WSL.