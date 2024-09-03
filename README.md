# How to EEG in a Driving Simulator

This repository serves as a source of materials to conduct EEG and ERP experiments in the driving simulator at the Department of Human Factors, Ulm University, Germany. All the information provided here is without warranty and is intended for educational and research purposes. Feel free to modify the contact information, protocols, or any other details to better fit your specific requirements.

Thanks to everyone who contributed to this collection of recommendations and guidelines for conducting and analyzing EEG experiments in our driving simulator in any way (analysis scripts, SILAB code, materials, and writing support for this manual), especially:
- Dr. Julian Elias Reiser
- Dr. Jürgen Pichen
- Dr. Philipp Hock
- Jasmin Leitner
- Anja Paulina Kolland
- Vanchha Chandrayan
- Anna Lisa Delp
- Alexandra Nick
- Leon Bach

### Citation

If you use the resources or code from this repository, please cite it as follows:<br />
Figalova, N. (2024). HuFa_Ulm_EEG: Materials for EEG Experiments in Driving Simulator. GitHub. https://github.com/yourusername/HuFa_Ulm_EEG

# 1. Some Very Basic Background Knowledge

Driver-vehicle interactions can be assessed using different approaches. Self-report measures are easy to implement; however, they might be overly simplistic. Performance measures can provide good sensitivity for differentiating high-demand performance tasks; however, they are rather inefficient when studying low- to medium-demand tasks. Another possible approach is to use psychophysiological data, which is becoming more convenient due to the increasing availability of relatively cheap and precise wearable sensors. Psychophysiological measures such as electroencephalogram (EEG), electrocardiogram (ECG), and electrodermal activity (EDA) can be used to assess drivers’ experience unobtrusively in real time. Disadvantages of psychophysiological measures include the need for special tools and equipment, expertise to collect and analyze the data, and possibly a high signal-to-noise ratio.<br />
For more details, see Cohen’s (2017) paper “Where Does EEG Come From and What Does It Mean?” and Luck’s (2014) book “An Introduction to the Event-Related Potential Technique”. The following text provides only a very broad introduction to EEG and ERP techniques.<br />

### 1.1. Basic Principles of EEG

Electroencephalography (EEG) is a prominent non-invasive technique used to record the electrical activity of the brain. This method involves measuring voltage fluctuations resulting from ionic current flows within the neurons of the brain. To capture these electrical patterns, electrodes are placed on the scalp using conductive gel to enhance signal quality.<br />
EEG is recognized for its exceptional temporal resolution, often in the range of milliseconds, allowing researchers to observe rapid changes in brain activity as they occur. However, it is worth noting that this method has relatively low spatial resolution, making pinpointing the exact origins of the recorded electrical activity within the brain challenging.<br />
<br />
The traditional approach to EEG involves an ongoing recording of brain activity. Analysts then examine the spectral properties of this activity in the frequency domain, exploring different bands of brainwaves (such as alpha, beta, delta, and theta waves) and their associations with various cognitive and emotional states.<br />

**Alpha Waves (8-13 Hz):** Predominantly present in the posterior part of the head and are more prominent when the eyes are closed and the person is relaxed. Alpha waves decrease in amplitude when the individual opens their eyes or engages in mental activities, making them associated with a state of calm, wakeful relaxation. In driving research, a decrease in alpha activity could indicate increased attention and alertness.<br />

**Beta Waves (13-30 Hz):** Found throughout various regions of the brain and are generally associated with active, alert, and attentive states. High levels of beta activity are linked to concentration, arousal, and engaged cognition. In the context of driving, increased beta activity could signify heightened focus and mental processing, especially during complex or demanding driving conditions.<br />

**Theta Waves (4-8 Hz):** Primarily observed in the frontal and middle regions of the brain and are typically associated with drowsiness, meditation, or early stages of sleep. In awake individuals, theta waves can also indicate deep internal focus, problem-solving, and memory encoding. In driving simulations, elevated theta activity could imply mental fatigue or a decrease in alert attention, which is crucial for identifying and preventing impaired driving performance.<br />

**Delta Waves (0.5-4 Hz):** The slowest of the brainwaves, delta waves are most prominent during deep, dreamless sleep and in very deep, meditative states. In awake individuals, an increase in delta activity may be associated with severe brain dysfunction. In driving simulations, delta activity is generally not expected to be prominent unless the participant is extremely fatigued or potentially asleep.<br />
<br />
Understanding the dynamics of these brainwaves and their implications for driver behavior and attention can provide invaluable insights in driving simulation research, aiding in the design of safer and more responsive vehicle systems.<br />

### 1.2. Basic Principles of ERP

Event-related potentials (ERPs) provide a different approach to analyzing brain activity. ERPs are time-locked responses to specific sensory, cognitive, or motor events. By averaging the EEG signal across numerous trials of the same event, ERPs isolate the brain’s response to that particular event, reducing the impact of non-event-related brain activity. The result is a waveform representing the brain’s response over time, with various peaks and troughs corresponding to specific cognitive processes.<br />
The ERP technique has been instrumental in shedding light on postsynaptic potentials of pyramidal neurons, offering insights into complex cognitive processes, including attention, perception, and decision-making. These insights are particularly valuable in contexts such as driver-vehicle interaction, where understanding how the brain processes information related to driving can inform the design of safer and more efficient vehicles.<br />
<br />
In the field of driving research, particularly in studies focusing on attention and fatigue, certain Event-Related Potential (ERP) components have been frequently studied due to their relevance and informative value. These include:<br />

**P300:** This positive deflection occurring around 300 ms after stimulus onset is commonly associated with cognitive processes related to attention and working memory. In driving research, the P300 is often analyzed in response to unexpected or rare events, serving as an indicator of the driver’s ability to allocate attention and process relevant stimuli. A decrease in P300 amplitude and an increase in latency are generally interpreted as signs of decreased attention and increased mental fatigue, which are critical factors in assessing driver readiness and performance.<br />

**N170:** This negative component, peaking around 170 ms post-stimulus, is typically linked to the processing of visual stimuli, particularly faces. In the context of driving, the N170 can be studied to understand how drivers respond to visual cues, such as road signs or facial expressions of other drivers or pedestrians. Analyzing changes in the N170 component can provide insights into the driver’s level of visual attention and fatigue.<br />

**N400:** This negative wave peaking around 400 ms is associated with semantic processing and the integration of information. In driving scenarios, studying the N400 component can reveal how efficiently a driver is processing and making sense of road signs, dashboard information, or navigational cues. An increase in N400 amplitude or latency might indicate cognitive overload or confusion, which is crucial information for assessing driver safety.<br />

By focusing on these or some of the many other ERP components, you can gain a more nuanced understanding of how drivers allocate attention, process visual and semantic information, and manage fatigue, ultimately contributing to the development of safer driving environments and more responsive vehicle technologies.<br />
<br />

### 1.3. Application of EEG and ERP in Driving Research

The versatility and non-invasive nature of EEG (Electroencephalography) measurement makes it a valuable tool for studying human cognition in various driving contexts. EEG provides real-time monitoring of brain activity, and when combined with event-related potentials (ERP), it offers deeper insight into the neural processes related to specific events or stimuli. In driving research, these measures are instrumental in understanding how drivers interact with their vehicles, particularly in the context of automated driving.

**Cognitive Demands of Vehicle Automation**
Attention and Workload Management: As vehicles advance towards higher levels of automation, understanding how these changes affect a driver’s cognitive load is crucial. EEG and ERP studies are pivotal in deciphering the fluctuations in attention levels and workload management across different automation levels. These studies can identify specific brain patterns associated with increased or decreased cognitive demands, helping in optimizing user interfaces and alert systems for better road safety.

**Decision-Making in Automated Vehicles**
Neural Mechanisms of Decision-Making: Automated vehicles require drivers to shift from an active controller to a supervisory role, altering the decision-making processes. EEG and ERP studies can unravel the complex neural mechanisms underlying these processes. They provide insight into how drivers evaluate situations, make judgments, and prepare to take over control when necessary, ensuring smoother human-machine interaction.

**Perception and Response to the Environment**
Cognitive Processes in Traffic Interaction: Driving in an automated vehicle necessitates a constant awareness of the surroundings, including recognizing traffic signs, other vehicles, and potential obstacles. EEG and ERP studies are vital in mapping the brain activity associated with these perceptual and cognitive processes. They help in understanding how information is processed and how timely and accurate responses are generated, contributing to safer driving practices.

**Mental Effort and Fatigue in Automated Driving**
Assessing Mental Drowsiness: Automated driving might induce a sense of relaxation, but it is imperative to monitor the potential mental drowsiness that can ensue. EEG is a crucial tool in this regard, as it can detect changes in brain activity patterns related to fatigue and mental effort. Understanding these patterns enables the development of alert systems that can notify drivers when their attention levels are waning, enhancing overall road safety.

**Impact of Distractions in Automated Driving**
Understanding Driver Distraction: In the realm of automated vehicles, driver distraction remains a significant concern, whether it stems from mobile phone usage or interacting with the vehicle's infotainment system. EEG and ERP studies illuminate the neural mechanisms underlying distracted driving. By identifying the brain activity associated with attention shifts and cognitive overload, these studies provide valuable insights that can be used to design more intuitive vehicle interfaces and distraction alerts.

Through these applications, EEG and ERP technologies prove to be indispensable in driving research, especially as we navigate the transition towards more automated vehicles. They offer a window into the human brain, providing essential data that can be used to enhance both vehicle design and driver safety. These studies not only contribute to our understanding of driver behavior but also pave the way for innovations that make automated driving safer and more efficient.

### 1.4. Recommended Literature
Lohani, M., Payne, B. R., & Strayer, D. L. (2019). A review of psychophysiological measures to assess cognitive states in real-world driving. Frontiers in human neuroscience, 13, 57.<br />

# 2. EEG Equipment Overview
### 2.1. Hardware 

1. LiveAmp amplifier <br /> <img src="https://github.com/nikol-figalova/images/blob/main/amplifier.jpg" width="30%">
2. Wireless trigger transmitter <br /> <img src="https://github.com/nikol-figalova/images/blob/main/trigger_transmitter.jpg" width="30%">
3. Trigger box and the wireless trigger receiver <br /> <img src="https://github.com/nikol-figalova/images/blob/main/trigger_extension.jpg" width="30%">
4. Recording laptop with the bluetooth receiver and the Recorder dongle <br /> <img src="https://github.com/nikol-figalova/images/blob/main/laptop_dongles.jpg" width="30%">
5. Bluetooth receiver<br /> <img src="https://github.com/nikol-figalova/images/blob/main/Dongle_bluetooth.jpg" width="30%">
6. USB stick with software and manuals<br /> <img src="https://github.com/nikol-figalova/images/blob/main/manuals_software.jpg" width="30%">
7. Dongle for the BrainVision Recorder<br /> <img src="https://github.com/nikol-figalova/images/blob/main/Dongle_recorder.jpg" width="30%">
8. Electrooculography (EOG) electrodes plugged in the BIP2AUX adapter<br /> <img src="https://github.com/nikol-figalova/images/blob/main/ECG_electrodes.jpg" width="30%">
9. EEG electrodes<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_electrodes.jpeg" width="30%">
10. Reference and ground EEG electrodes<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_reference_electrode.jpeg" width="30%"><br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_grounding_electrode.jpeg" width="30%">
11. Cable to connect the amplifier with the trigger extension<br /> <img src="https://github.com/nikol-figalova/images/blob/main/cable2.jpeg" width="30%">
12. Cable to connect the power bank with the amplifier<br /> <img src="https://github.com/nikol-figalova/images/blob/main/USBadapter.jpg" width="30%">
13. Power bank with charger<br /> <img src="https://github.com/nikol-figalova/images/blob/main/powerbank.jpeg" width="30%">
14. Clip to fix the amplifier to the seat belt<br /> <img src="https://github.com/nikol-figalova/images/blob/main/clipper.jpg" width="30%">
15. EEG caps<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG-cap)sizes.jpg" width="30%">
16. Dummy head<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_dummyhead.jpg" width="30%">
17. EEG cap size mark<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_cap_size.jpeg" width="30%">

### 2.2. Consumables 
1. Disinfection for the skin under the EOG electrodes<br /> <img src="https://github.com/nikol-figalova/images/blob/main/desinfection.jpg" width="30%">
2. Shampoo for participants <br /> <img src="https://github.com/nikol-figalova/images/blob/main/shampoos.jpg" width="30%">
3. Syringes for EEG gel with Luer-lock<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_syringe.jpeg" width="30%">
4. Blunt needles with 14G Luer-lock<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_LeuerLock_BluntNeedle.jpg" width="30%">
5. Adhesive circles for the EOG electrodes<br /> <img src="https://github.com/nikol-figalova/images/blob/main/adhesive_rings.jpg" width="30%">
6. Cotton pads<br /> <img src="https://github.com/nikol-figalova/images/blob/main/Cotton_tampons.jpg" width="30%">
7. Abrasive electrolyte gel for EOG electrodes<br /> <img src="https://github.com/nikol-figalova/images/blob/main/ECG_abrasive_gel.jpg" width="30%">
8. EEG gel<br /> <img src="https://github.com/nikol-figalova/images/blob/main/EEG_gel.jpg" width="30%">

Additionally, it's important to prepare bottled water and snacks (sweets work particularly well) as the process can be lengthy, and you want your participant to remain as comfortable as possible. 

For participants to clean their hair after the experiment, you'll need to provide shampoo and towels. I recommend purchasing a few different types of shampoo, which can be reimbursed—just speak with our secretary about the process. Towels are also essential for participants to dry their hair after washing. You can pick up towels from the post office; currently, they are available for collection on Wednesdays from 13:45 to 14:15, but this schedule may change. 

Ensure that you always have fresh EEG gel available for experiments. The shelf life of an opened EEG gel is about 12 months (be sure to write the opening date on the gel pack), but in my experience, they can sometimes dry out faster. If the gel dries out, it may be difficult to achieve the low impedance required, as the conductivity will be poor. Always check the EEG gel well in advance and order new supplies from BrainProducts if needed. Keep in mind that it can take a few weeks for them to process and ship your order. While it's important not to over-order, it's better to have a little extra on hand than to run out during an experiment. 

# 3. Software Requirements 
To visualize the EEG signals during setup, you'll need the BrainVision Recorder. This tool allows you to monitor the electrode resistance and visualize the data in real-time. 

For recording data, you have two options: BrainVision Recorder or LSL Recorder. 

**BrainVision Recorder:** This software can be installed from the provided USB stick, which also contains manuals. Alternatively, you can download the software from the BrainVision website. Follow the installation instructions available on the USB stick or the website. To use the BrainVision Recorder, ensure the BrainVision Recorder Dongle is plugged into your laptop. 

**LSL Recorder:** While the LSL Recorder can also be used for data recording, its main advantage lies in the synchronization of different data streams. Depending on your experimental design, it may be easier to record data directly with triggers sent from the simulator rather than using LSL. However, if you plan to integrate additional data streams (e.g., secondary tasks in PsychoPy), LSL may be the better choice. 

To synchronize data with the driving simulator, you can use the TCP trigger receiver and transmitter. Alternatively, you can use the Lab Streaming Layer (LSL). For more information and installation instructions, visit the LSL website: Lab Streaming Layer.  

The advantage of using LSL is its easy integration with PsychoPy. PsychoPy is a powerful software tool based on Python that allows you to create psychophysiological experiments using either code or a graphical user interface (GUI). It’s a free tool with extensive online support and tutorials. Learn more at PsychoPy.  

You can also use BrainVision Analyzer for data pre-processing. This software might be easier for novice users due to its graphical user interface and ease of navigation. However, it offers limited options compared to EEGLab, which provides greater flexibility and is thus the recommended tool.



## 3.1. Setting Up Workspace for Data Recording 
### 3.1.1. BrainVision Recorder 
### 3.1.2. LSL Recorder 


# 4. EEG Set Up

To record your data, you'll need to set up all the electrodes. Typically, you'll want to record horizontal eye movements along with the EEG signals. Note that I have never recorded vertical eye movements, as they are well reflected in the electrodes placed just above the eyebrows.

### 4.1. Electrooculography (EOG)

It's recommended to set up the EOG electrodes before placing the EEG electrodes. To record horizontal eye movements, you'll need a set of three electrodes connected to a BIP2AUX adapter, which is plugged into the trigger extension box (AUX1).

ECG electrodes with the BIP2AUX adapter: 
<br /><img src="https://github.com/nikol-figalova/images/blob/main/ECG_electrodes.jpg" width="30%">
<br />Trigger extension with the trigger receiver: 
<br /><img src="https://github.com/nikol-figalova/images/blob/main/trigger_extension.jpg" width="30%">

- The **blue** and **green** electrodes should be connected to the positive and negative poles of the adapter and placed at the outer corners of the participant’s eyes.
- A **grounding electrode** (black) is also needed for recording and should be placed on the left mastoid.

Ensure consistency across participants by always placing the blue electrode on the left eye and the green on the right eye.

The electrodes should be placed as shown:

<br /><img src="https://github.com/nikol-figalova/images/blob/main/EOG_outer_plus_mastoid.jpg" width="30%">
<br /><img src="https://github.com/nikol-figalova/images/blob/main/EOG_outher.jpg" width="30%">

### Steps for Electrode Placement:

1. Clean the skin with disinfectant.
2. Place an adhesive ring on the electrode.
3. Remove the paper backing from the ring.
4. Position the electrode on the skin and apply gentle pressure to ensure it is securely attached.
5. Fill the electrode opening with abrasive gel using a syringe.
6. Repeat these steps for all three electrodes.
7. Check the signal in the BrainVision Recorder by asking the participant to look left and right, ensuring the recorded signal is correct.

### 4.2. Electroencephalography (EEG)
For the electrode placement, follow these steps:

1. Measure the size of the head at its widest part using a measuring tape.
2. Choose the appropriate cap size (currently, we have 54, 56, 58 cm). If the participant is in between sizes, choose the smaller one. If we don't have the exact size, select the closest one.
3. Place the cap on the head. The positioning is specified in the BrainVision user manual. Generally, the front of the cap should be right above the participant's eyebrows. Use the measuring tape to ensure the cap is centered.
4. Participants who wear glasses can put them back on now.
5. Close the velcro under the participant’s chin. Ensure the cap is stable but not too tight—you should be able to fit two fingers under it, but comfort varies by participant.<br /><img src="https://github.com/nikol-figalova/images/blob/main/EEG_cap_space.jpg" width="30%">
6. Plug the electrodes into the openings of the cap. You can do this before the experiment or while participants are filling in questionnaires. Use the dummy head for this. Ensure that the electrodes are not tangled, as this could damage them and cause additional noise in your signal.<br /><img src="https://github.com/nikol-figalova/images/blob/main/EEG_dummyhead_cap.jpg" width="30%">
7. Connect the electrodes to the LiveAmp and clip the electrodes to the participant's t-shirt using the clip on them. This will prevent unnecessary movement of the electrodes and improve data quality. <br /><img src="https://github.com/nikol-figalova/images/blob/main/EEG_electrode_click.jpg" width="30%">. 
8. Connect the LiveAmp to the BrainVision Recorder.
9. Apply conductive gel to each electrode, starting with the ground and reference electrodes. Use gentle pressure on the skin and, with the tip of the needle, push the hair aside. Use the needle to exfoliate the skin and remove dirt and sweat. Be careful not to hurt participants, and ensure it’s not too harsh for them.<br /><img src="https://github.com/nikol-figalova/images/blob/main/EEG_gel_filling.jpg" width="30%">
10. Check the impedance level in the BrainVision Recorder. Ideally, keep the impedance under 10 kΩ. While the manual states that values under 25 kΩ are acceptable, I recommend going as low as possible. As Steve Luck points out, there is no substitute for clean data. If the impedance is too high, try applying more gel, scratching the skin a bit more, or pressing the electrode more firmly onto the scalp. However, avoid creating conductive bridges between different electrodes.
11. One by one, fill all the electrode caps. With some participants, the impedance may decrease on its own after a few minutes. I recommend first applying the conductive gel to all electrodes using only gentle scratching with the needle, then checking each one for impedance and making adjustments until you reach the desired level.
12. Once all electrodes are at the desired impedance level, the participant is ready for the experiment. This is a good time to ask if they need to use the toilet before starting.
13. Offer water and snacks to participants at this point, as food and drinks should not be brought into the driving simulator.
14. Bring the participant to the simulator. After they adjust the seat, ask them to put on the seatbelt and attach the amplifier to the seatbelt using the clipper. This will prevent unnecessary movement of the electrodes and improve data quality.<br /><img src="https://github.com/nikol-figalova/images/blob/main/EEG_simulator_setup.jpg" width="30%">
15. Perform the experiment.
16. After the experiment, remove the amplifier from the seatbelt, pick up the power bank and the extension, and bring the participant to the Fokusgrupenraum.
17. Open the velcro under the chin. If the participant wears glasses, ask them to remove them now.
18. Remove the electrode cap. Be gentle—don’t pull too hard, as some hair might be caught in the electrode openings during setup. **NEVER PULL ON THE ELECTRODES.**
19. Gently remove the EOG electrodes.
20. Once the cap is removed, unplug it from the amplifier, as well as the EOG.
21. Cover the end of the EEG electrodes and the BIP2AUX adapter in a clean, dry towel.
22. Place the electrodes in a bowl of lukewarm water with the towel protecting the electrode electronics.
23. Now, instruct the participant on how to wash their hair in the sink. Show them the shampoo options and provide a clean, fresh towel. Some participants may not mind if you stay in the room to clean up; others may prefer privacy.
24. While the participant washes their hair, unplug the electrodes from the cap. **NEVER pull the electrodes by the cable**—snap them out of the electrode holder. Leave both the cap and the electrodes in the bowl of water. Also, check the headrest in the simulator for any leftover gel and clean it if necessary.
25. Once the participant has washed their hair, offer them a hairdryer.
26. Finalize the experiment—collect signatures, complete questionnaires, handle reimbursement, debrief, etc.
27. Say goodbye to the participant.
28. Place the EEG cap and electrodes in the bowl to soak. Keep the electronics tightly wrapped in a towel on the edge of the sink.
29. Using a toothbrush and lukewarm water, gently clean the electrodes one by one. Clean the EEG cap as well, ensuring no gel remains.
30. Hang the electrodes to dry on the clothes rack next to the wardrobe. Keep the electronics wrapped in the towel placed on top, and leave the electrodes hanging.

If not in use, store the electrodes in the wardrobe. Always handle the electrodes with care—they are fragile and expensive. If one breaks, it could take several weeks to resolve, which you definitely don’t want in the middle of your experiment.

Keep the wardrobe organized and clean. Use the organizers to keep everything in its place. Avoid the following:<br /><img src="https://github.com/nikol-figalova/images/blob/main/Storage_bad.jpg" width="30%">

# 5. Data Pre-Processing and Analysis

This will depend on your experimental setup and research questions. For general guidelines, Steve Luck and Mike X Cohen were the best resources. An absolute gold for me was the book Applied event-related potential data analysis by Steven Luck. Its an online book, available for free, and shows step by step how to pre-process and analyse ERP data. To help understanding the actual analysis, Analyzing neural time series data: theory and practice is priceless. Finally, the BeMoBil pipeline by Marius Klug is a great, reproducible approach to analyse your mobile data. In this repository, you can find the code that is based on this pipeline and which can be reused for your own data whenever applicable. 

For data analysis, I strongly recommend using Matlab with the EEGLab Extension. During my work, I utilized the following plugins:
- Darbeliai v2022.12.22.1
- ERPLAB v9.00
- FMUT v0.5.1
- Fieldtrip-lite v20230202
- ICLabel v1.4
- Mobilab v20210924
- TFA v20221221
- bemobil-pipeline v1.9
- bva-io v1.71
- clean_rawdata v2.7
- dipfit v4.3
- firfilt v2.6
- xdfimport v1.18
- zapline-plus v1.2.1

As far as I know, there is currently a new verison of EEGLab (2024), which offers a major improvement compared to the previous versions. I highly recommend getting into MATLB over using BrainVision Analyser. If you prefer Python, consider the FieldTrip toolbox. I decided for MATLAB because I feel there is more online resources and more support from my network. However, MATLAB is expensive. You have to make this decision based on your perosnal preference and skills - if you know Python, it might not be worth it getting into EEGlab, and vice versa. Both offer wide range of options for data preprocessing and analysis. 

### 5.1. Recommended Literature
Cohen, M. X. (2017). Where does EEG come from and what does it mean?. Trends in neurosciences, 40(4), 208-218.  
Cohen, M. X. (2014). Analyzing neural time series data: theory and practice. MIT press.  
Luck, S. J. (2014). An introduction to the event-related potential technique. MIT press.
Luck, S. J. (2022). Applied event-related potential data analysis. LibreTexts.[Google Scholar].

# 6. Tips and Good Practices 
Over time and with experience, you'll figure out what works best for you. Below are general recommendations I've collected over the years of conducting EEG experiments. These could be useful when planning your first driving simulator or real-world EEG experiments.

### Before the Experiment 

**Ethical Approval**
- The application must be written in German. Ask a native German speaker to proofread it, as the ethics committee will return the form for revision if there are grammar mistakes. This is likely due to legal reasons.
- The committee meets once a month, and the meeting dates can be found on their website. They usually accept applications up to 2 weeks before the meeting, so make sure to submit it on time for the intended meeting. However, if there are too many applications, the committee might push yours to the next month's meeting. In this case, you should be informed. 
- The committee typically sends several rounds of revisions, but these can be submitted on a rolling basis, and the revisions are discussed between meetings. 
- The longest approval process I've experienced was 14 months (due to collaboration with an industrial partner and various issues). Generally, I recommend applying as soon as possible, at least 3 months before you plan to collect data.
- Once you have an initial ethical approval, and if you are conducting similar experiments, you can submit an amendment to the existing approval.
- An example application for ethical approval can be found in the repository section.

**Instructions to Participants**
- Participants should sleep as usual before the experiment and avoid alcohol or substances that impact their vigilance in the 24 hours prior.
- Participants used to drink coffee or energy drinks regularly can drink these as they are used to in orther to avoid bias in your data. 
- Instruct them to wash their hair the evening before or the morning of the experiment. Ask them not to use **any** hair products, as this significantly reduces the signal quality and increases your setup time. 
- Provide detailed directions to the lab, including a map, as a room number alone is not sufficient. Include parking information, especially if participants are not Ulm University students.
- If you need them to fill out questionnaires before they arrive, send these well in advance (I typically sent them 24 hours prior).
- Remind participants of their appointment the day before and summarize what they should do, should not do, bring, and complete before arriving at the lab.

## General Recommendations
**Environmental Noise:** Real-world experiments will have more environmental noise than simulator experiments. I recommend using a larger sample size to ensure sufficient statistical power. Check the sample size of others using similar paradigms and adjust accordingly. Generally, aim for a minimum of 20 participants in a driving simulator and 30 in real-world settings, but ideally, scale up by 5-10 participants if resources allow.

**Channel Density:** High-density systems offer better spatial resolution, which aids in data cleaning using independent component analysis (ICA). Although we currently have a 32-channel EEG system, I recommend upgrading to a system with more electrodes.

**Sampling Frequency:** A sampling frequency of 500 Hz has proven sufficient. Data recorded at higher resolutions can be down-sampled to 500 Hz before analysis.

**Impedances:** In mobile environments, impedances should be kept as low as possible, ideally below 10 kΩ. While I kept them below 25 kΩ in my experiments, aiming for lower values is advisable for future studies.

**Pilot Trials:** Schedule several pilot participants on different days before starting actual participant recruitment. This ensures that both hardware and software are working flawlessly. Aim for 2-3 pilot participants, ideally friends who are flexible and can provide feedback. Allow yourself time between pilots to optimize based on any issues identified.

**Data Control:** After each pilot trial, review the dataset to ensure everything is recorded correctly and that the triggers are accurate.

**Pilot Data Pre-processing:** Pre-process and analyze the pilot data according to the planned pipeline. This helps identify any potential issues early on, avoiding major problems later.

**Audio-Visual Material:** Collect sufficient audio-visual material during trials for future presentations and publications. Take photos of participants in the simulator, the secondary task, and other relevant aspects. To avoid bureaucracy, consider using pilot participants who agree to appear in publications or take photos from angles that don't show faces.

**Laboratory Consumables:** Before each experiment, test all equipment to ensure everything is in working order. Be mindful that consumables like electrolyte gels can dry out between experiments, and supplies like syringes may run out. It takes time to get these delivered, be sure to stock up in good time before the experiment. 

**Documentation:** Document every step in detail at every stage of the experiment—planning, execution, data pre-processing, and analysis.

**Participant Notes:** Keep detailed notes on each participant, noting any non-standard situations, comments, extended setup times, simulation crashes, or breaks during trials. Use a shared online spreadsheet for all team members to record these notes.

**Pre-registration:** Pre-registering EEG/ERP studies is useful for avoiding publication issues due to lack of significant effects and helps eliminate bad scientific practices such as data manipulation or p-hacking.

**Real-world Testing:** Whenever possible, conduct tests in a realistic environment rather than relying solely on a driving simulator.

**Refreshments:** Keep participants hydrated and fed during EEG experiments. Always have water (still and sparkling) and snacks available, considering food allergies. Avoid offering tap water as it tastes unpleasant in the Focus Group Room.

**Toilet Breaks:** Encourage participants to use the toilet after the EEG cap is mounted but before the experimental trial begins.

**No Pain Induced:** Emphasize that EEG gel application can be uncomfortable but should not be painful. Instruct participants to notify you immediately if they feel pain. This precaution helps avoid complaints about bruises or scratches, and it’s advisable to include this information in the consent form and reiterate it verbally.

**Two-Person Setup:** Having two researchers present during EEG setup is recommended to speed up the process and ensure the participant is never left alone with a single researcher, which could lead to problematic situations.

**Setup Time Variability:** Be prepared for varying EEG setup times with each participant. Times can range from 7 to 80 minutes with the same 32-channel system. On average, plan for 20-30 minutes per participant with two moderately experienced researchers, doubling this time if less experienced.

**Buffer Time:** Schedule extra time between participants to account for potential delays during EEG setup. This reduces stress and ensures smooth scheduling.

**Standardized Instructions:** Use standardized video instructions for participants, especially when multiple researchers are involved in data collection, to minimize bias.

**Online Questionnaires:** Opt for online questionnaires whenever possible to save transcription time and minimize the risk of human error.

**Participant Preparation:** Ask participants to arrive with freshly washed, dry hair without any hair products, as this significantly improves data quality and reduces setup time. Participants with long hair should keep it loose. Participants with glasses should remove them during cap placement but can wear them afterward.

**Kochlear Implants:** Note that it is not possible to record data from participants with a cochlear implant.

**Electrode Application:** Always inform participants that electrode application might be slightly unpleasant but should not hurt. If they feel pain, be gentler. Show them that you are using a blunt needle by poking it on your hand to demonstrate its safety.

**Consumables:** Use syringes and needles with a Luer Lock, available on Amazon. Determine the best size for your needs, with size 14 being a good starting point. Always check consumable stock before experiments as receiving new supplies can take time. Be mindful that EEG gel has a shelf life of around 12 months, and even if it looks okay, it may degrade data quality over time.

**Data Backup:** Always check your data after each recording, save it with a proper name or code, and make a backup copy. Remember: no backup, no mercy.

**Pilot Tests:** Running a pilot test is crucial, and potentially several may be necessary. Have the pilot participant complete the entire experiment to uncover any issues that might arise later. Ensure all data is logged correctly and all triggers are saved accurately. It's advisable to have two researchers present during the setup and throughout the experiment whenever possible.

## Final Notes
The experimental setup is highly individual and influenced by various factors, including researcher experience, participant hair and skin type, weather, and more. With experience, setup time will likely decrease, but some factors are beyond your control. Realistically, expect setup times between 30 and 90 minutes.

Keeping participants comfortable is key—engage in light conversation or allow for quiet time based on their preference. Stressed participants may sweat, which could negatively impact your signal quality.





<img src="" width="30%">
<br /> <img src="" width="30%">



ToDo: 
- LSL connection
- Study Manager (TCP)
- PsychoPy experiment
- 3.1.  setting up workspace
- example ethics approval
- example instructions



