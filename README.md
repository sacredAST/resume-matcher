<div align="center">

[![Resume Matcher](Assets/img/Resume_Matcher_GitHub_Banner.png)](https://www.resumematcher.fyi)

# Resume Matcher

### Resume Matcher is an AI Based Free & Open Source Tool. To tailor your resume to a job description. Find the matching keywords, improve the readability  and gain deep insights into your resume.

</div>

<div align="center">

**Don't let your resume be a roadblock from getting your next job. Use Resume Matcher!**

![Resume_Matcher_streamlit_demo](Assets/img/Resume_Matcher_Gif.gif)

## How does it work?

</div>

The Resume Matcher takes your resume and job descriptions as input, parses them using Python, and mimics the functionalities of an ATS, providing you with insights and suggestions to make your resume ATS-friendly.

The process is as follows:

1. **Parsing**: The system uses Python to parse both your resume and the provided job description, just like an ATS would.

2. **Keyword Extraction**: The tool uses advanced machine learning algorithms to extract the most relevant keywords from the job description. These keywords represent the skills, qualifications, and experiences the employer seeks.

3. **Key Terms Extraction**: Beyond keyword extraction, the tool uses textacy to identify the main key terms or themes in the job description. This step helps in understanding the broader context of what the resume is about.

4. **Vector Similarity Using FastEmbedd**: The tool uses [FastEmbedd](https://github.com/qdrant/fastembed), a highly efficient embedding system, to measure how closely your resume matches the job description. The more similar they are, the higher the likelihood that your resume will pass the ATS screening.

<br/>

<div align="center">

## How to install

</div>

Follow these steps to set up the environment and run the application.

1. Fork the repository [here](https://github.com/srbhr/Resume-Matcher/fork).

2. Clone the forked repository.

   ```bash
   git clone https://github.com/<YOUR-USERNAME>/Resume-Matcher.git
   cd Resume-Matcher
   ```

3. Create a Python Virtual Environment:

   - Using [virtualenv](https://learnpython.com/blog/how-to-use-virtualenv-python/):

     _Note_: Check how to install virtualenv on your system here [link](https://learnpython.com/blog/how-to-use-virtualenv-python/).

     ```bash
     virtualenv env
     ```

   **OR**

   - Create a Python Virtual Environment:

     ```bash
     python -m venv env
     ```

4. Activate the Virtual Environment.

   - On Windows.

     ```bash
     env\Scripts\activate
     ```

   - On macOS and Linux.

     ```bash
     source env/bin/activate
     ```

    **OPTIONAL (For pyenv users)**

   Run the application with pyenv (Refer this [article](https://realpython.com/intro-to-pyenv/#installing-pyenv))

   - Build dependencies (on ubuntu)
      ```
      sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python openssl
      ```
      ```

      sudo apt-get install build-essential zlib1g-dev libffi-dev libssl-dev libbz2-dev libreadline-dev libsqlite3-dev liblzma-dev libncurses-dev

      sudo apt-get install python-tk python3-tk tk-dev

      sudo apt-get install build-essential zlib1g-dev libffi-dev libssl-dev libbz2-dev libreadline-dev libsqlite3-dev liblzma-dev

      ```
   - pyenv installer
     ```
        curl https://pyenv.run | bash
     ```
   - Install desired python version
     ```
       pyenv install -v 3.11.0
     ```

   - pyenv with virtual enviroment
     ```
        pyenv virtualenv 3.11.0 venv
     ```

   - Activate virtualenv with pyenv
     ```
        pyenv activate venv
     ```

5. Install Dependencies:

   ```bash
   pip install -r requirements.txt
   ```

6. Prepare Data:

   - Resumes: Place your resumes in PDF format in the `Data/Resumes` folder. Remove any existing contents in this folder.
   - Job Descriptions: Place your job descriptions in PDF format in the `Data/JobDescription` folder. Remove any existing contents in this folder.

7. Parse Resumes to JSON:

   ```python
   python run_first.py
   ```

8. Run the Application:

   ```python
   streamlit run streamlit_app.py
   ```

**Note**: For local versions, you do not need to run "streamlit_second.py" as it is specifically for deploying to Streamlit servers.

**Additional Note**: The Vector Similarity part is precomputed to optimize performance due to the resource-intensive nature of sentence encoders that require significant GPU and RAM resources. If you are interested in leveraging this feature in a Google Colab environment for free, refer to the upcoming blog (link to be provided) for further guidance.

<br/>

### Docker

1. Build the image and start application

   ```bash
       docker-compose up
   ```

2. Open `localhost:80` on your browser

<br/>

### Running the Web Application

The full stack Next.js (React and FastAPI) web application allows users to interact with the Resume Matcher tool interactively via a web browser.

> [!WARNING]
> The results returned from through the web app are currently entirely mocked / faked. This means that the results returned are not real and are just for demonstration purposes. This will be implemented with real data results in a future release.

To run the full stack web application (frontend client and backend api servers), follow the instructions over on the [webapp README](/webapp/README.md) file.

<br/>

### Google Colab
1. Create an account in ngrok and get you token
2. ![img_1.png](img_1.png)
3. Go to archive/resume_matcher_colab.ipynb and run the notebook.
4. Enter your ngrok token and run the notebook.
5. Copy the url and open it in your browser.
6. ![img_2.png](img_2.png)

## Code Formatting

This project uses [Black](https://black.readthedocs.io/en/stable/) for code formatting. We believe this helps to keep the code base consistent and reduces the cognitive load when reading code.

Before submitting your pull request, please make sure your changes are in accordance with the Black style guide. You can format your code by running the following command in your terminal:

```sh
black .
```

## Pre-commit Hooks

We also use [pre-commit](https://pre-commit.com/) to automatically check for common issues before commits are submitted. This includes checks for code formatting with Black.

If you haven't already, please install the pre-commit hooks by running the following command in your terminal:

```sh
pip install pre-commit
pre-commit install
```

Now, the pre-commit hooks will automatically run every time you commit your changes. If any of the hooks fail, the commit will be aborted.

#### Tech Stack

![Python](https://img.shields.io/badge/Python-FFD43B?style=flat-square&logo=python&logoColor=blue) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) ![Next JS](https://img.shields.io/badge/Next-black?style=flat-square&logo=next.js&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat-square&logo=fastapi) ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white) ![& More](https://custom-icon-badges.demolab.com/badge/And_More-white?style=flat-square&logo=plus&logoColor=black)

<br/>