# **Stroop Task**


![Stroop](https://github.com/ThipkanlayaJaiaue/adaptive-executive-function-tasks/blob/main/Inhibition-Stroop/adaptiveStroop.gif)

This repository contains Stroop tasks in different conditions, as used in <u>**Differential Contributions of Inhibition and Task Engagement to Workload: Evidence from a Novel Adaptive Stroop Task**</u> (Jaiaue et al., 2026; https://doi.org/10.1080/00140139.2026.2702629).

* stroop_practice
* stroop_control
* stroop_standard
* stroop_adaptive

It also includes a processing script '*processData.py*' to process collected data into a dataframe.

###### *All tasks are compatible with *PsychoPy version 2025.1.1**

---

### Task Configuration

- **Control:** Congruent trials only, with a fixed trial duration based on familiarisation.
- **Standard:** Equal numbers of congruent and incongruent trials, with a fixed trial duration based on familiarisation.
- **Adaptive:** Equal numbers of congruent and incongruent trials. Trial duration was initially set based on familiarisation and adjusted on a trial-by-trial basis for incongruent trials.

**Trial randomisation:** Trials were presented in random order, subject to the following constraints:
- No more than two consecutive congruent or incongruent trials.
- No two consecutive trials of the same congruency shared the same response key.
- Each of the four colours appeared in at least 20% of trials, independently for word content and font colour.


---



### 🔧 **Task setup and modification instructions (user-friendly version)**



#### **1. For all tasks (including practice)**



* **Stimulus sequence** controlled in the stimuliCode component (End Routine) of the `sequenceGeneration` routine.

      - *Trial number* → trialAll_num (line 4) ⚠️ Must be equal

      - *Congruent vs. incongruent proportion* → trialCongruent_proportion (line 5)

      - *Pool of Stroop words and colours* → pool (line 33)

      - *Word and colour distribution criteria* → line 76

      - *Key responses* → lines 82–85 ⚠️ Must also match the allowedKeys field for the stroopResp component in both `practiceTrial` and `experimentalTrial` routines



* **Feedback (text, colour, sound)** controlled in the fbCode component (Begin Routine) of the `practiceTrial_feedback` or `blank` routine.



* **Data identification and recording** controlled in the addData component (End Routine) of the `practiceTrial` or `experimentalTrial` routine.



#### 

#### **2. Stroop Practice**



* **Initial trial duration (calculation)** controlled in the fbCode_2 component (Begin Routine) of the `practiceBlock_feedback` routine.



* **Target accuracy** controlled in the fbCode_2 component (End Routine) of the `practiceBlock_feedback` routine.



* **Practice repetition (if accuracy not met)** controlled in the nReps field of the `practiceRepetition` loop.



#### 

#### **3. Stroop Experimental Tasks**

###### **⚠️ Important: Experimental tasks only run if a practice file with the same participant ID exists.**



* **Practice file path** controlled in the fetchPracticeData component (Begin Experiment, line 5) of the `sequenceGeneration` routine. ⚠️ Ensure that data_files (line 5) is updated to match the path to your data folder


* **Initial trial duration** controlled in the addData component (Begin Routine, line 3) of the `sequenceGeneration` routine.



* **Adaptation criteria (adaptive task only)** controlled in the addData component (End Routine, lines 27–33) of the `experimentalTrial` routine.


---


### 🗃️ **Process the data**

Data collected from the task can be processed using *processData.py*.
⚠️ Ensure that stroop_folder (line 6) is updated to match the location of your data folder.


---
### ❝ ❞ **How to cite**

**Gallicchio, G., & Jaiaue, T. (2025). Adaptive-Stroop-task. Zenodo. https://doi.org/10.5281/zenodo.17014552**

---

**Questions or bug reports?**
📧 Please contact: thipkanlayajaiaue@gmail.com

