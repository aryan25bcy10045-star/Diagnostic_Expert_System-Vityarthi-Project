# Project Title:-
AI-Driven Expert Medical Diagnostic System (VITYARTHI PROJECT)

# Overview:-

This project is a hybrid intelligent diagnostic system that integrates:

1:-Rule-Based Reasoning using SWI-Prolog

2:-Machine Learning Classification using Python + scikit-learn

3:-Interactive GUI using Tkinter

The system collects user symptoms, evaluates them using Prolog rules (from rules.pl), predicts the most likely medical diagnosis, suggests a treatment plan, and also uses a machine-learning model to estimate a risk level (Low / Medium / High).

The project showcases a powerful combination of symbolic AI and statistical learning—making it perfect for academic demonstrations, research, and intelligent system design.

# Features:-

1. Prolog Rule-Based Diagnosis

All medical inference logic is stored in rules.pl.

----> Python asserts symptom facts dynamically:

@ symptom(patient, fever_high).

@ symptom(patient, duration_long).


----> Prolog determines the diagnosis using rules:

@ severe_infection

@ acute_infection

@ mild_viral_fever

@ prolonged_fever

@ no_clear_diagnosis


----> Treatment recommendations are mapped using:

@ treatment(Diagnosis, TreatmentText).

----> Python retrieves output via:

@prolog.query("get_diagnosis(X, T)")

2. Machine Learning Risk Prediction

ML model implemented using DecisionTreeClassifier.

Training data loaded from symptoms_data.csv.

Model saved as risk_classifier.pkl.

Automatically trains itself if model not found.


----> Predicts:

@ Low risk

@ Medium risk

@ High risk


3. Graphical User Interface (GUI)

Built with Tkinter
Clean UI with dropdowns, text inputs, and results windows.

----> Displays:
@ Diagnosis (from Prolog)
@ Treatment (from Prolog)
@ Risk level (from ML model)

Automatic validation for numeric inputs.

4. Fully Modular Architecture
   
----> Component	Description

app.py	GUI + Python ↔ Prolog integration + ML predictions

classifier_model.py	ML training + risk prediction

rules.pl	Medical rules, diagnosis logic, treatment plans

symptoms_data.csv	Training dataset

requirements.txt	Python dependencies

# Technologies & Tools Used:-

----> Programming Languages


@ Python

@ Prolog (SWI-Prolog)

----> Python Libraries

@ pyswip – Prolog integration

@ scikit-learn – ML model

@ numpy – numerical tasks

@ joblib – saving ML model

@ tkinter – GUI


----> Software Tools

@ SWI-Prolog

@ Python 3.10+

# Installation & Setup Guide:-

1:- Install SWI-Prolog

Download here:
https://www.swi-prolog.org/download/stable

Verify installation:

"swipl --version" (IN TERMINAL)

2:- Clone the Project
git clone <https://github.com/aryan25bcy10045-star/Diagnostic_Expert_System-Vityarthi-Project> , 

(OPEN CODES AND ESSENTIAL FOLDER AND DOWNLOAD)

cd Diagnostic_Expert_System

3:- Create Virtual Environment (Optional)

python -m venv venv

source venv/bin/activate        # macOS/Linux

venv\Scripts\activate         # Windows

4:- Install Python Dependencies

----> From requirements.txt:

scikit-learn

numpy

joblib

pyswip


Install:

"pip install -r requirements.txt"

5:- Ensure Required Files Exist

----> Make sure the following are in the same directory:

app.py

classifier_model.py

rules.pl

symptoms_data.csv

requirements.txt

The file risk_classifier.pkl will be auto-generated.

6:- Run the Application

python app.py


----> On the first run you may see:

----> Initial run detected. Training the Classification Model...

This is normal — it builds the ML model.

# Testing Instructions:-

1:- Test Prolog Rules

Open Prolog:

'swipl rules.pl'


Run:

get_diagnosis(X, T).

2:- Test ML Classifier

python classifier_model.py


----> Expected output:

Test Prediction (39.0 C, 5 days): High

3:- Test GUI Behavior

Run:

python app.py


----> Test:

High fever + long duration → severe infection

Low fever + short duration → mild viral fever

No fever → no_clear_diagnosis

Risk prediction should update accordingly.

-------->    About rules.pl (Knowledge Base Explanation)

@ Your rules.pl contains:

- Dynamic Facts
- dynamic symptom/2.


Python inserts symptoms dynamically using PySWIP.

- Diagnosis Rules

Example:

diagnosis(severe_infection) :-
    symptom(patient, fever_high),
    symptom(patient, duration_long).


----> Other rules include:

acute_infection

mild_viral_fever

prolonged_fever

no_clear_diagnosis

- Treatment Recommendations

Example:

treatment(mild_viral_fever,
  'Low to medium risk: drink plenty of fluids...').

- Main Prolog Entry Function
get_diagnosis(Diagnosis, TreatmentText) :-
    diagnosis(Diagnosis),
    treatment(Diagnosis, TreatmentText).

Python calls this directly.


# Project Structure:-

Diagnostic_Expert_System/

│── app.py

│── classifier_model.py

│── rules.pl

│── symptoms_data.csv

│── requirements.txt

│── risk_classifier.pkl       # Auto-generated

│── README.md

#SCREENSHOTS

<img width="662" height="581" alt="MAIN INTERFACE" src="https://github.com/user-attachments/assets/0bba56ae-bd2b-44d6-ab36-8a6752b80dd5" />

<img width="656" height="578" alt="OUTPUT 1" src="https://github.com/user-attachments/assets/ac49ced1-b998-4386-92b7-8c0bb47d6b49" />

<img width="640" height="557" alt="OUTPUT 2" src="https://github.com/user-attachments/assets/c8ec03ea-0c00-4e1a-ad32-89a5dd748ff2" />

<img width="641" height="577" alt="OUTPUT 3" src="https://github.com/user-attachments/assets/c16feed7-75d1-4137-b3cd-24e3dd778c60" />

<img width="626" height="560" alt="OUTPUT 4" src="https://github.com/user-attachments/assets/ef2eb84e-bd8f-4199-94a9-cb8f952531c4" />

<img width="658" height="581" alt="OUTPUT 5" src="https://github.com/user-attachments/assets/d42e40dd-68b9-4cf8-b9f9-2bb53085bca3" />

<img width="626" height="576" alt="OUTPUT 6" src="https://github.com/user-attachments/assets/ff7fb6ab-16fa-4c6d-9c55-315243ccabfd" />

<img width="648" height="583" alt="OUTPUT 7" src="https://github.com/user-attachments/assets/8cc24a8d-bb33-40a7-a5ea-98aeab01706e" />
