# Creating and validating emails for a certain sector of New Zealand businesses

Part of the work I did while at Decisive.

I have created a set of code which takes in a business type, for example "plumbers", and return a list of ALL plumbers in New Zealand with their emails (where possible).

- First it scraps the Google Place search API and rotates through every suburb in New Zealand to return a comprehensive list of plumbers in New Zealand with their corresponding company information.
- Then it scraps the NZBN API, and for each business records the directors name and where exist a contact email.
- For those without an email from NZBN, the code scraps google searches for the business's domain name. 
- A email is generated by concatenating the first name of the director of the business with the company domain name.
- The generated email is then verified using an external API, "whoisxml".

This is purely for marketing purposes - for reaching out to a certain sector of New Zealand business without manually looking up each and every email address. An advantage is that it often picks up the director's email instead of the enquiries email (which they often list on their websites), and theoretically enhance the promotion. 

If you go through the code you will realize that there is a .env file that has not been uploaded on to github. That file contains the API keys to the Google API, the NZBN API, and also the Whoisxml API. 

# Files in the package

All the files are required for the code to run successfully. 
- api_funcs.py contain code for all the API calls.
- conf.py contains the references to our dot env file.
- main.py is the ONLY file we need to RUN. But it needs to be in the same folder as all the other files. You can edit main.py to get emails for your desired business type.
- misc_variables.py contains miscellaneous variables, such as the very long list of all suburbs in NZ.
- util.py contain utility functions.
