User Story 1 - Informed consumer
Karen is a proud owner of a cellular device and your average well informed technology enthusiast. Currently, Karen is looking to purchase a new cellular device, and wants to know which newest phone model will have the longest lasting battery life to make the most informed decision. Karen is proficient at navigating websites, but doesn’t have a technical background. Therefore, Karen is looking for a simple interface that allows her to select a phone model(s) (i.e., battery chemistrie(s)), and it will output an estimated “lifetime” of the phone battery.

Use Case: which newest phone model will have the longest lasting battery life

Component Design - Describe what the system does?
●	User: Selects a battery chemistry
●	System: Accesses a database on said chemistry
●	System: Processes database files into workable dataframe
●	System: Displays what variables/column headers were extracted
●	System: Asks user to select features of interest to train model on, and suggests recommendations based on the data extracted from the column headers 
●	User: Inputs features of interest
●	System: Recognizes Ambient temperature was selected as a feature
●	System: Displays all ambient temperatures tested within the dataframe, and prompts user for temperature(s) to train model on
●	User: Selects ambient temperature(s) of interest
●	System: Reprocess dataframe to work only with users selected  ambient temperature
●	System: Tests for various (linear) correlations within dataframe of selected features
●	System: Outputs correlations and asks user what to train model on 
●	User: selects feature(s) to train model
●	System: Double checks user has selected the “best” correlation to train model on. If not, prompts them are they sure they want to continue
●	User: If user selected any option but the “best correlation” they will need to “confirm” to continue to train the model 
●	System: Trains ML model on random sample within the dev data frame containing features of interest
●	System: Trained ML model is tested on the test data frame dataframe containing features of interest to compare 1) capacity retention prediction and/or 2) estimated cycle # at which 80% capacity with #% confidence
●	Plots




User Story 2 - Battery Researcher
Paul is a battery researcher. He has been working in the battery field for over 10 years. He wants to predict how long battery life will be without testing it for days. He usually assembles different kinds of batteries, like different types of cathode or anode. With the tool, he could find a battery that have better performance. Paul doesn’t have a software technical background, he is only good at excel or some other analytical tools. Paul is looking for something that helps him test the battery degradation in a more efficient way, and output lifetime of the battery.

Use Case: estimate/predict battery life on as few cycles as possible with a high level of confidence 

Component Design - Describe what the system does?
●	User: Input the file which have first few cycles of the battery
●	System: Read the file
●	System: Processes database files into workable dataframe
●	System: Displays what variables/column headers were extracted
●	System: Asks user to select features of interest to train model on, and suggests recommendations based on the data extracted from the column headers 
●	User: Inputs features of interest
●	System: Recognizes Ambient temperature was selected as a feature
●	System: Displays all ambient temperatures tested within the dataframe, and prompts user for temperature(s) to train model on
●	User: Selects ambient temperature(s) of interest
●	System: Reprocess dataframe to work only with users selected ambient temperature
●	System: Tests for various (linear) correlations within dataframe of selected features
●	System: Outputs correlations and asks user what to train model on 
●	User: selects feature(s) to train model
●	System: Selects “best” correlation to train model
●	System: Trains ML model on random sample within the dev data frame containing features of interest
●	System: Trained ML model is tested on the test data frame dataframe containing features of interest to compare 1) capacity retention prediction and/or 2) estimated cycle # at which 80% capacity with #% confidence
●	System: 
●	System: Asks user to select the plot graph of interest (for example, cycle number vs. capacity)
●	User: Select plot graph that interest
●	System: output the graph User selected

 







User Story 3 - Process/Environmental Engineer 
Hugh wants to reduce over-purchasing of chargeable batteries for their vehicle fleet and reduce waste production/management costs, as well as be able to predict when the best “time” to recycle the materials within a battery. Hugh is really good at Excel!!! That’s it though, he would not find a raw script useful. Not even VBL….so I guess not that good at Excel. Hugh values a simple user interface that would have a clear and relatively short SOP so that he can train entry level employees to do it for him. A tool that generates results that can be related to cost directly would also be really useful for selling this service to a client.

From the consumption perspective, from the production perspective → Warranty

Looking at the model for prac use case in an Environmental Industrial setting. 1) Manufacturer offering warranty 2) Keeping track of when/the time battery should be recycled/replaced.

The specific specs dont need to be here for now. 

BG: New data has shown that exposure to heat and the use of fast charging promote the degradation of Li-ion batteries more than age and actual use, and that the average electric vehicle battery will retain 90% of its initial capacity after six years and six months of service. For example, the battery in a Nissan Leaf will degrade twice as fast as the battery in a Tesla, because the Leaf does not have an active cooling system for its battery.

Requirements: Easily searchable specs of a commercially available battery. Here is an example I found of a car battery that can be purchased (it is fast charging….) but here is the info available:
Which type of battery you would want to buy. Req should go more into the details, and 
●	Battery Chemistry : Lithium Iron Phosphate seems like the most commonly available based on a quick Goog
●	Ampere-Hour Capacity: 60 Ah , which will deliver a current of 3A for 20 hours (this would be the constant current mode for discharge? Or we could at least assume it is constant in this case, maybeeee look at the “non constant” data too)
●	Current Modes for discharge : 100A max continuous discharge, 750A max 2 second pulse, 650A max 5 sec pulse. The flat discharge voltage curve provides a 75% bigger capacity than a 60Ah SLA battery
●	Energy in Watt hours : 720 Wh
●	Battery Lifespan : Up to 80% capacity for 2,000 cycles in recommended conditions. The typical SLA has 500 cycles. Dakota Lithium batteries last so long that the price per use is a fraction of traditional batteries
●	Operating Temperature : Ideal for rugged & harsh environments. Much better than SLA or other lithium batteries. -20°F min, +150°F max optimal operating temps (battery performs well down to -20°F). Avoid charging below 32°F. Discharge cut off at - 20°F/-20°C. Charge cut off at 23°F/-5°C. BMS high temp cut off at 167°F / 75°C

Describing a Use Case

System: Prompts for battery voltage, Ampere-Hour Capacity, Available Modes for Discharge, approx. operating temperature or range of temperatures for the process of interest (or ideally process of interest and manual would show what range of temp is used for each process).
System: Also has prompts for units of Temperature but certain prompts will have default units that cannot be changed
User: Fills out prompts based on purchased batteries or batteries looking to be purchased
System: 
Models capacity over time for each experiment set in the NASA dataset as the “training set”, generates data based on given parameters to create the “modeled set” shows plots for reference. Manual will include an SOP for what the plot is showing (we love visualizations)
(Practically if this was an ongoing project you could add more to the training set over time and add classifications, I was previously a data annotator for a data science team and we were scraping and generating data for them constantly to train their NL processing model for each patch or new feature)
User response: Prompts for a report in the form of a spreadsheet to print out and show client or save for reference as they take inventory (they have to do this every year for all of their batteries anyways)













User 4 Story - Technician
Sean is a data scientist who is good using machine learning techniques to predict properties in several domain. To make the model that predicts the lifetime of a battery more robust, he need to retrain/finetune it when there are new data added into the original dataset. He would be glad if there is a clear direction to help him figuring out where to reach out to new data. After the model is trained successfully, he would also like to compare its performance with other models.

Use Case: add new data to a given battery chemistry database and retrain model

Component Design - Describe what the system does?

System: Login your account, customer or technician
User: Choose “technician” and enter account information
System: Parse account information and match them with technician database.
System: [Successful]
System: Display main page, e.g., four boxes directing users to “Model detail”, “Data”, “Training history”, and “Model training”.
User: Select either category. (For example, click “Model retrain” page).
System: Directing to “Model training” page.
System: Select which model architecture wants to be trained, select which dataset is used, and select “Train from scatch” or “Finetune the model”
User: Click one of the architecture (feed hyperparameters as well), dataset, choose finetune the model.
System: Check if the model setting matches with any training history. If yes, raise error “This model setting has been trained on {dataset_name} before!”, else: pass.
System: Read the checkpoint .json file containing the training results from last training process (lr, steps, )
















































User 5 - Policy Writer 
Bobby G is a policy writer working in the White House. As the United States shifts towards electrifying its transportation and energy generation sectors, he recognizes the criticality of writing new policy that protects and maintains the newly installed energy infrastructure (i.e., where/when installations should be installed, how often should they be maintained, what is their lifetime, ect.). For the policy to be effective, Bobby G needs to have a solid grasp of how the batteries being used in energy storage units are degrading as a function of time and environmental conditions. Bobby G does not have a background in battery science, but is technically inclined and proficient with statistics. Therefore, Bobby G wants to easily access a database of a particular chemistry battery he knows is going to be installed in a given average ambient temperature, and get an estimate cycle # as to when said batteries will reach the end of second life.

Use Case: in a given average ambient temperature what is the estimated cycle life said batteries will reach the end of first/second life?

Component Design - Describe what the system does?
●	User: Selects a battery chemistry
●	System: Accesses a database on said chemistry
●	System: Processes database files into workable dataframe
●	System: Displays what variables/column headers were extracted
●	System: Asks user to select features of interest to train model on, and suggests recommendations based on the data extracted from the column headers 
●	User: Inputs features of interest
●	System: Recognizes Ambient temperature was selected as a feature
●	System: Displays all ambient temperatures tested within the dataframe, and prompts user for temperature(s) to train model on
●	User: Selects ambient temperature(s) of interest
●	System: Reprocess dataframe to work only with users selected  ambient temperature
●	System: Tests for various (linear) correlations within dataframe of selected features
●	System: Outputs correlations and asks user what to train model on 
●	User: selects feature(s) to train model
●	System: Double checks user has selected the “best” correlation to train model on. If not, prompts them are they sure they want to continue
●	User: If user selected any option but the “best correlation” they will need to “confirm” to continue to train the model 
●	System: Trains ML model on random sample within the dev data frame containing selected features of interest
●	System: Trained ML model is tested on the test data frame dataframe containing features of interest to compare 1) capacity retention prediction and/or 2) estimated cycle # at which 80% capacity with #% confidence






