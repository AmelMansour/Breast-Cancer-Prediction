# Breast-Cancer-Prediction

The goal of our study is to predict in silico the mutations affecting the BRCA1 and BRCA2 genes, responsible for breast cancer, in order to identify similar patterns associated with deleterious effects. By combining sophisticated computational techniques and valuable biological data, this model is able to accurately discern whether a genetic mutation presents a pathogenic risk or is inconsequential.

1. Importing Libraries:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/13585f43-99d0-4f01-8990-48b3d079608e)

These lines import the necessary libraries, including pandas for data manipulation and Google Colab files for loading and saving files.

2. Loading CSV Files:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c8e16dbb-40a9-499c-ad2c-01e6c6b7b61f)

These lines load two CSV files, clinvar_resultBRCA1.csv and clinvar_resultBRCA2.csv, into two distinct DataFrames (df1 and df2). The sep parameter is used to specify the delimiter that separates values in the CSV file (in this case, the semicolon ; is used as the delimiter).

3. Concatenating the DataFrames:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ee766178-0e4d-4b91-9149-982cd6f3e645)

This line concatenates the two DataFrames (df1 and df2) into a single DataFrame called df. The argument ignore_index=True ensures that the index is reset, so the resulting DataFrame has continuous indexes starting from zero.

4. Saving the DataFrame to a CSV file:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fd71eb3a-e3f3-4aff-b2a0-ff24eac4816c)

These lines save the DataFrame df into a CSV file named BRCA.csv. The argument index=False tells pandas not to include the index column in the final CSV file. The file path is specified as '/content/BRCA.csv', and this path can be used to access the saved file.

5. Importing Libraries:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/1b5f1af8-e0d5-4ca2-99f4-a579ad9156d9)

These lines import the necessary libraries, including pandas for data manipulation and re for regular expression processing.

6. load_and_clean_data Function:
This function takes two arguments: input_file (the name of the input CSV file) and output_file (the name of the output CSV file).

7. Loading the DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/522ce24c-6f35-42e7-a2b7-e3c7f8387a81)

This line loads the DataFrame from the specified input CSV file input_file.

8. Regular Expression for Extracting Information:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/6f80a7d5-0ede-482d-a88c-33dbc361d778)

r: The r prefix before the string indicates a raw string in Python. This means that escape characters like \ are treated literally and are not interpreted. This is commonly used for regular expressions in Python.

(p.: This part of the regular expression matches the string "(p." literally in the text you are searching for. Parentheses () are special characters in regex, so to include them literally, they are escaped with \.

([A-Za-z]+): This part captures a group of one or more uppercase or lowercase letters (at least one letter) and stores it as a capturing group. The square brackets [A-Za-z] define a character class that matches any letter from the alphabet, both uppercase and lowercase. The + means that there must be at least one letter.

(\d+): This part captures a group of one or more digits (at least one digit) and stores it as another capturing group. The \d matches any decimal digit (0 to 9), and the + means that there must be at least one digit.

9. Applying the Regular Expression and Creating New Columns:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/97ae1e36-9115-4ee7-bd51-bc95cf8d0c6b)

This line applies the regular expression to the "Name" column of the DataFrame to extract information such as the wild-type amino acid, position, and mutated amino acid. This information is stored in the extracted_info DataFrame.

10. Adding New Columns to the Original DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/0a63ab19-4dfb-4858-a602-6baadf38dcf8)

These lines add three new columns to the original DataFrame (df) to store the extracted information: "AcideAmineSauvage", "Position", and "AcideAmineMute".

11. Selecting Columns to Display:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d2a10a4d-93b6-4260-b82b-c98bc78fc796)

These lines select specific columns from the original DataFrame (df) that you want to display and store them in a new DataFrame called displayed_df.

12. Saving the Displayed DataFrame to an Output CSV File:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/da716d21-7f07-407e-a5e3-2079ffbd73d3)

This line saves the displayed_df DataFrame into an output CSV file specified by output_file. The index=False argument ensures that the index column is not included in the final CSV file.

13. Calling the load_and_clean_data Function with the Specified Input and Output Files:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ca3d93ca-8cf4-4536-93e2-2f0723a3701b)

These lines call the load_and_clean_data function with the input and output file names, performing all the operations described above.

14. Displaying the Resulting DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/0c380fe8-9aff-4a45-b5d6-f5f46355f435)

This line displays the resulting DataFrame.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/a45d48fd-5dc1-43f9-9077-c8c1530dcc58)

--> This result corresponds to a DataFrame that has been cleaned and prepared from the original data. Here's what the different columns mean: 

• Name: This is the name of the genetic variation. It includes information such as the version number (NM_007294.4 for BRCA1 and NM_000059.4 for BRCA2) and the notation of the genetic variation (c.4631C>T). 

• WildTypeAminoAcid: This is the original amino acid before the genetic mutation. For example, "Pro" means proline. 

• Position: This is the position of the mutation in the genetic sequence. For example, "1544" indicates position 1544. 

• MutatedAminoAcid: This is the amino acid resulting from the genetic mutation. For example, "Leu" means leucine. 

• Clinical significance (Last reviewed): This is the clinical significance of the genetic variation as last reviewed. For example, "Conflicting interpretations of pathogenicity" means there are conflicting interpretations of the pathogenicity of the variation. 

• GRCh37Location: This is the location of the genetic variation on the GRCh37 version of the human genome. It gives the position of the variation on this version of the genome. 

• GRCh38Location: This is the location of the genetic variation on the GRCh38 version of the human genome. It gives the position of the variation on this version of the genome.

The DataFrame contains a total of 3091 rows and 7 columns, meaning there are 3091 distinct entries of genetic variations with their associated details.
This dataset is well-prepared for analyzing and visualizing genetic variations in the BRCA1 and BRCA2 genes, providing important information about the position, type of mutation, and clinical significance of each variation.


 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/e1cc63b9-36e5-497c-9925-4bada57b0b17)

• file_path = '/content/displayed_dataframe.csv': This line of code defines the variable file_path as a string containing the path to the CSV file where you want to save the DataFrame. The path /content/displayed_dataframe.csv indicates that the file will be saved in the /content/ directory with the filename displayed_dataframe.csv.

• displayed_df.to_csv(file_path, index=False): This line of code uses the to_csv method of the displayed_df DataFrame to save its contents into a CSV file. Here's what the arguments passed to this method do:

file_path: This is the path of the CSV file where the data will be saved, as defined earlier.

index=False: The index argument is set to False, meaning that the DataFrame's index (row numbers) will not be included in the saved CSV file. This is often done when the index doesn't hold any specific meaning and you don't want it included in the final CSV file.


15. Importing Libraries:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/535e37b4-94c7-46a3-b2e4-440351742c4f)

We import the Pandas library for data manipulation.

16. Loading the DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d00baeef-bf87-40d9-b7e6-9849f0aeb677)

We load a DataFrame from a CSV file called 'displayed_dataframe.csv'.

17. Data Cleaning Function:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b90da7ae-130c-4f8f-b3e5-d4fb28b35f7a)

We define a function called clean_displayed_data that takes a DataFrame df as input.

18. Removing Duplicate Rows:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/4acb85ef-013a-4bbd-b71e-c74952abbbf1)

We use the drop_duplicates() method to remove duplicate rows from the DataFrame.

19. Removing Rows with Missing Data (NaN):

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/950c8473-8895-4942-b8c5-edd5e29569b2)

We use the dropna() method to remove rows containing missing (NaN) values in any column of the DataFrame.

20. Reindexing the DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/7f6812fb-4466-4184-823c-70ef1c69e79a)

We reindex the DataFrame after performing the deletions to reorder the row indices.

21. Removing Rows Containing "None" Values in Any Column:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/649eecac-1ac2-4508-9d87-920f71b605d4)

We use dropna() with the argument how='any' to remove rows containing "None" values in any column of the DataFrame.

22. Correcting Incorrect Values in the "Position" Column:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ad1c6add-3583-4d3e-b0df-ae881871a0fc)

We define a function correct_position that attempts to convert the value in the "Position" column to an integer. If the conversion fails (e.g., if the value is not a valid number), we return None.

23. Applying the Correction to the "Position" Column:
    
 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/252d8624-9d4e-4207-9a86-bb693a74163d)

We apply the correct_position function to the "Position" column of the DataFrame to correct the incorrect values.

24. Removing Missing Data (NaN) in the "AcideAmineSauvage" Column:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d284cd79-e66e-45f0-b36c-aa28efe166b4)

We use dropna() to remove rows with missing (NaN) values in the "AcideAmineSauvage" column.

25. Displaying the Cleaned DataFrame:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d1766efa-956e-43fb-a70f-e640de55cebc)

We display the cleaned DataFrame after performing all the cleaning steps.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fb22fb06-4014-4701-8a94-7451dfa23570)

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c8b5cb5e-1187-4a11-a280-11d0033eda58)

--> By combining these cleaning steps, the function clean_displayed_data(df) ensures that the resulting DataFrame, cleaned_df, contains only valid and consistent data, which is essential for accurate and reliable analysis.
The DataFrame contains a total of 2277 rows, each representing a different genetic variation with its associated characteristics.


26. Importing the Pandas Library for Data Manipulation:
   
 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d40c31eb-10c8-49ac-838f-a30cfdbcfed5)

27. Defining a Function display_unique_values that Takes a DataFrame df and a List of Column Names columns_to_check as Arguments. This Function Will Display the Unique Values for Each Specified Column:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/3b7c986e-07c2-46d8-ba67-ccfa0f326afd)

28. Loading the DataFrame from the "displayed_dataframe.csv" File:
    
![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/3ca868be-d036-4825-98a5-5d11032645fd)

29. Selecting Relevant Columns You Want to Check for Unique Values. In This Case, the Columns "AcideAmineSauvage" and "AcideAmineMute" are Selected:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/52f63b2b-b115-4c71-961f-2a7446e67caf)

30. Calling the display_unique_values Function with the DataFrame displayed_df and the List of Columns to Check:
 
![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b584b975-1a8a-4310-ba7a-35d6ef56d27b)

31. Importing Necessary Libraries:

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/bc6194ca-cae0-4b8b-bc63-59ec9d81ff9c)

32. Loading a DataFrame from the "displayed_dataframe.csv" File:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c92390ee-0a07-488a-9931-be06b916ad49)

33. Creating a List of Amino Acids Called acides_amines for Later Use:

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b760d9be-ed91-4521-9661-49d945e29401)

34. Initializing an Empty List resultats_filtrations to Store the Filtering Results:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fa92d799-bac1-4d50-a542-ec0540a3d74b)

35. Initializing the Output Widget output_text to Display Results:
    
 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/8ca36407-8a93-4273-a740-2d4066722c13)

36. Defining a PDF Class for Generating PDF Reports Using the fpdf2 Library:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/026d2f41-53c4-4af8-8f75-967975736c42)

37. Defining a generate_pdf Function to Generate a PDF Report Containing the Filtering Results:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/8f303149-37ac-4860-8506-c8f0ddf32366)

38. Defining a filter_records Function to Filter Records from the DataFrame Based on Amino Acid and Position:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/6216bde6-eaa3-480d-8e23-0f50e8f0b3d7)

39. Defining Button Click Handlers (on_continue_button_click and on_stop_button_click) to Handle User Actions:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b2b9cdcd-0932-4982-8eff-0e235a7bdc50)

40. Creating an HTML Link (link) to Download the Results as CSV Files:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/39f32e51-5f06-42ba-80c2-3069184cf82c)

41. Defining a display_results Function to Display the Filtering Results in the Output Widget output_text:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/acc8a2ce-b0f5-4410-b067-0e296fa8f0b0)

42. Defining a display_widgets Function to Display Interactive Widgets for the User to Enter Amino Acid and Position Values, as Well as a Filtering Button:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/451cda1c-19d2-49f7-ae89-372aba80a946)

43. Calling the display_widgets Function to Display the Interactive Widgets:
    
 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/048de45e-9c47-4d98-945f-0a1610ff828c)

44. Displaying the Link to Download the Generated CSV Results:

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/647209c1-d849-48d4-bf1c-cf915a2b30d0)

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/82967cf2-3fe3-4324-a3f7-d75581a0b1e8)

This code will allow you to select an amino acid and position, display the results with the current date and time, and then ask the question, "Do you want to continue?" If you choose "Yes," the process will repeat with a new amino acid and position. If you choose "No," the code will display "Execution finished." and show the final output of the datetime.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ebcfde61-0a0f-41aa-9c6e-b0690a081277)

It will display all the filtering results performed from the beginning when you click the "Stop" button. The results of each filtering are stored in the resultats_filtrations list and are displayed one by one when the "Stop" button is clicked.



![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/adf66514-c094-42bb-9bbe-00ba8d873857)

# Conclusion

In conclusion, bioinformatics predictive models play a crucial role in evaluating mutations in the BRCA1 and BRCA2 genes. Through a combination of advanced computational techniques and biological data, these models can determine whether mutations are pathogenic or neutral, guide clinical decisions, and facilitate cancer research by leveraging large databases and machine learning methods to improve their accuracy. As such, they have become an important tool in medical genetics, enabling a better understanding of genetic mutations and taking preventive measures to reduce the risk of hereditary cancers.

