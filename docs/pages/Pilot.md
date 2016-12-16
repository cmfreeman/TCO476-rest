---
layout: page
title: "Airline Resource"
permalink: /airlineresource/
--- 
# Overview  
The Pilot Resource allows the user to receive information regarding a specific pilot and add new pilots to the API.  

# Output Information Fields  
The information provided by the resource is as follows:  
- **Pilot Name:** The name of the pilot.
- **Pilot ID Number:** The ID number of the pilot within the API.  
- **Airline ID:** The ID number of the Airline for which the pilot is flying.  

# Use  
The Pilot Resource can be accessed by the input of a unique URL. The URL uses server information and pilot ID to provide the output.  
  
  **URL:** http://server/api/pilot/id  
  
## Example:  
For this example, we will use the following information to create our URL:  
**Server:**  54.167.221.72   
**Pilot ID:** 1   

The resulting URL is:  
http://54.167.221.71/api/pilot/1  
  
Using this URL, the following output is received:  

{  
    "PilotId": "1",  
    "LastName": "Watson",  
    "FirstName": "Bob",  
    "AirlineId": "1"  
}  
  
From this output, the following information is obtained:  
- **Pilot ID:** 1  
- **Pilot Name:** Bob Watson  
- **Airline ID:** 1  
