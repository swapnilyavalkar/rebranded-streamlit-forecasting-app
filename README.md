# Rebranded Streamlit Forecasting App

An interactive time series forecasting web app built using Streamlit and Facebook Prophet. Upload your data, visualize trends, and generate future forecasts with minimal code.

This project is a rebranded version of a Streamlit app for forecasting using **Prophet**. The app is deployed on **WSL** (Windows Subsystem for Linux) and includes customization options like links for support and improvement requests.

---

## **Prerequisites**
1. **Install Python 3.7, 3.8, or 3.9** in your WSL environment.
   To check and set up the WSL environment with Python, follow the steps below:

   ```bash
   wsl --list --online
   wsl --install -d Ubuntu-20.04
   sudo apt update
   sudo apt-get upgrade
   python3 --version
   cd /path/to/rebranded-streamlit-forecasting-app/
   sudo apt install python3.8  # Only if Python 3.8 is not already installed
   sudo apt install python3.8-venv
   ```

2. **Set up a Python Virtual Environment**:
   After ensuring Python is installed, create a virtual environment and activate it:
   
   ```bash
   python3 -m venv streamlit_prophet_env
   source streamlit_prophet_env/bin/activate
   ```

3. **Install Required Dependencies**:
   Install essential libraries and Prophet along with the required packages:
   
   ```bash
   sudo apt install -y build-essential python3-dev libatlas-base-dev gfortran libssl-dev libcurl4-openssl-dev
   pip install -U pip
   pip install pystan==2.19.1.1
   pip install altair==4.1.0
   pip install prophet
   python -c "from prophet import Prophet; print('Prophet installed successfully')"
   ```

4. **Install Streamlit Prophet App**:
   Clone and install the Streamlit Prophet app from GitHub:
   
   ```bash
   pip install git+https://github.com/artefactory-global/streamlit_prophet.git@main
   streamlit_prophet deploy dashboard
   ```

## **Customization**

### **Logo Customization**
To customize the logo used in the app, replace the existing logo file in the following location:

```bash
/path/to/rebranded-streamlit-forecasting-app/streamlit_prophet_env/lib/python3.8/site-packages/streamlit_prophet/references/logo.png
```

### **Link Customization**

- **Logo file being used**:  
  The logo file is loaded from the path above using the following code in the app:

  ```python
  st.sidebar.image(load_image("logo.png"), use_column_width=True)
  ```

- **Links for Help and Improvement Requests**:  
  The links for help and improvement requests are managed in the `config_readme.toml` file:

  ```bash
  /path/to/rebranded-streamlit-forecasting-app/streamlit_prophet_env/lib/python3.8/site-packages/streamlit_prophet/config/config_readme.toml
  ```

  Modify the email links as follows:

  ```toml
  [links]
  # Email link for queries
  help = "mailto:support@example.com?subject=Need%20Help%20on%20Streamlit%20Portal&cc=admin@example.com"

  # Email link for improvement requests
  improvement_request = "mailto:support@example.com?subject=Streamlit%20Improvement%20Request&cc=admin@example.com"
  ```

## **Display Links in the App**
The `display_links` function is defined in the following file:

```bash
/path/to/rebranded-streamlit-forecasting-app/streamlit_prophet_env/lib/python3.8/site-packages/streamlit_prophet/lib/exposition/export.py
```

### **Display Links Code**:
This function dynamically displays the "Need Help?" and "Suggest Improvements" links in the sidebar:

```python
def display_links(repo_link: str, article_link: str) -> None:
    """Displays a repository and app links.

    Parameters
    ----------
    repo_link : str
        Link of git repository or email link.
    article_link : str
        Link of medium article or email link.
    """
    st.markdown(
        f"""
        <div style='display: flex; justify-content: center; gap: 20px;'>
            <a style='text-decoration: none; color: #007bff;' href='{repo_link}'>Need help?</a>
            <a style='text-decoration: none; color: #007bff;' href='{article_link}'>Suggest Improvements.</a>
        </div>
        """,
        unsafe_allow_html=True,
    )
```

## **Running the Application**
Once everything is set up, you can run the app with the following command:

```bash
streamlit run /path/to/rebranded-streamlit-forecasting-app/streamlit_prophet_env/lib/python3.8/site-packages/streamlit_prophet/app/dashboard.py OR streamlit_prophet deploy dashboard
```