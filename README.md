# Dependent-Field-on-Salesforce-Form-on-Site

The images below show the creation of a dependent field called 'Sub-Industry'. According to the user selection on the Indsutry field above it will display the appropriate picklist values. Those values come from the gov.uk site. Due to the volume of those values, a programmatic approach was needed.
(As this is a real world example implemented by me on behalf of a previous employer, no code files will be available). The images below show the related code written for this fucntion and the UI result.

The implementation has as follows:

A new field has been added to the current form called Sub-Industry. It is only visible when an Industy Sector value has been chosen in the field above. Then according to the option in the parent, the Sub-Industry field will display the relevant options to choose from. 
A Custom metadata type was created to represent the new field type and the values available in this field have been inserted as Metadata Records.

The following two images display the visual result, according to two different sections the sub-Industry field display different values.
![Screenshot 2022-03-10 at 15 09 59 (2)](https://user-images.githubusercontent.com/97835800/158820726-6459516d-2181-48e9-9d72-5d5b669b5081.png)

![Screenshot 2022-03-10 at 15 09 51 (2)](https://user-images.githubusercontent.com/97835800/158820739-ff98dad6-6640-41d0-ad11-6da610a440d7.png)

Use of lightning:select tag to implement the new dropdown field.
<img width="579" alt="Screenshot 2022-03-10 at 15 10 39" src="https://user-images.githubusercontent.com/97835800/158822870-788dfb0c-8857-438e-a9b5-3aab0b4fd63a.png">

Aura Javascript Controller file. It retrieves the metadate records according to the Industry selection by calling an apex method.
<img width="677" alt="Screenshot 2022-03-10 at 15 11 31" src="https://user-images.githubusercontent.com/97835800/158822951-8b9b69bf-e2dd-48d6-8f9d-e82179d854f5.png">

Apex Controller. Returns the metadate records by calling another method, the soql access method. (As a best practice the data access methods are hold in different classes than the business logic).
<img width="803" alt="Screenshot 2022-03-10 at 15 10 59" src="https://user-images.githubusercontent.com/97835800/158823154-18dabd0a-f526-43a1-9371-d92305044fc4.png">

Apex Class, it accesses the records and sends them to the Apex Controller class.
<img width="809" alt="Screenshot 2022-03-10 at 15 11 15" src="https://user-images.githubusercontent.com/97835800/158823541-e19c7f5c-bfad-4db8-ab53-1934c3d52933.png">

