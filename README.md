# Rhythm
This is the repository for the heart arrhythmia detection project for HackWestern 6 (2019) 

## Inspiration

The prominence of cardiovascular disorders has only gotten worse resulting in 30% of deaths worldwide according to the World Health Organization. Therefore, it is crucial to detect patients at risk earlier and better understand the mechanism of disease to prevent the onset of cardiac arrest. A common routine used in hospitals is the acquisition of **electrocardiograms (ECG)** to capture the cardiac electrophysiology propagation in the heart using a non-invasive method. 
Our team wanted to find a convenient way to assess the electrophysiology of patients at risk and detect cardiac arrhythmias to alert caregivers or medical aid of the arrhythmic state and risk of cardiac arrest. 

## What it does
We developed **Rhythm**, a wearable device that routinely evaluates a patient’s ECG and inputs it into a model generated by a machine learning algorithm. If the model predicts that the patient is experiencing a state of arrhythmia, it immediately calls a caregiver who can talk to a bot that has access to the patient data. 

## How We built it
**The Hardware** 
We used an Arduino Pro Mini with an FTDI basic breakout as for microcontroller communication. The ECG signals are measured by a single lead AD8232 and sent to the PC as an analog signal. 

The team built a convolutional neural network in the tyhoe VGG16 to process these 1-d signals into a single value which is stored in a csv file. This single value was obtained through the complex analysis of the P, R, S and T values associated with each heartbeat. 

The convolutional neural network uses artificial intelligence and deep learning to train a model that can use the values in the csv file to accurately predict when and what type of heart arrhythmia will occur. The group designed a algorithm that when fed testing data, generates a .h5 model that can be indefinitely trained to further the accuracy in diagnosing possible heart abnormalities.

The group used over half a million different patient data sets to train the neural network to become more and more accurate as time goes on. With over 7 hours of training the model, we have achieved an accuracy rating of over 99.7%. 

It should be noted that the group did indeed discuss another simpler path to success which included transposing the 1-D ECG signals to a 2-d grayscale image and then using a neural network to identify what type of heart beat was occurring through image recognition with the help of ImageNet. However, the group decided that said path would be vulnerable to scaling issues and run-time efficiency.

Once the model detects with a high degree of certainty that a the patient is experiencing cardiac arrhythmia, and there is potential for entry into cardiac arrest, it uses the Twilio API to call a caregiver at least twice, in the event that the caregiver does not respond, 911 will be dispatched immediately. 

Through the use of Twilio API, we have created a voicebot that relays important information to the caregiver such as location of the patient, their heartbeat and the diagnosis.

## Challenges we ran into
When we first built the hardware to analyze the ECG, there was a huge learning curve. By the time we finally got it to work, we had already begun working on the machine learning model and incorporating the different aspects of the program together. At some point Saturday evening, the hardware stopped working and we could not get it to work despite hours of troubleshooting. Thankfully, we had a backup of each of our hardware elements and so we re-built the hardware from scratch. 

We got it working only to find out that our Twilio account that we used to contact the caregivers got suspended as we uploaded our code to GitHub. Turns out that our Authentication ID and token were not allowed to be made public as it is a security breach risk. 

## Accomplishments that we’re proud of
This was all of our first time using any machine learning software. We spent dedicated hours learning how to train models and how to use the models to predict the outcome of new data. 

## What we learned
This was one of our first opportunity to work on a extensive project with a group. Over the 36 hours, we improved our ability to delegate tasks and organize the workflow to ensure efficiency and quality was met. 

# Rhythm-HackWestern6
