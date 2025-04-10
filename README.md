# Breast-Cancer-Prediction

The goal of our study is to predict in silico the mutations affecting the BRCA1 and BRCA2 genes, responsible for breast cancer, in order to identify similar patterns associated with deleterious effects. By combining sophisticated computational techniques and valuable biological data, this model is able to accurately discern whether a genetic mutation presents a pathogenic risk or is inconsequential.

# Bioinformatics Section

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

Nous importons la bibliothèque Pandas pour la manipulation des données.

16.	Chargement du DataFrame :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d00baeef-bf87-40d9-b7e6-9849f0aeb677)

Nous chargeons un DataFrame à partir d'un fichier CSV appelé 'displayed_dataframe.csv'. 

17.	Fonction de nettoyage des données :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b90da7ae-130c-4f8f-b3e5-d4fb28b35f7a)

Nous définissons une fonction appelée clean_displayed_data qui prend en entrée un DataFrame df.

18.	Suppression des lignes en double :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/4acb85ef-013a-4bbd-b71e-c74952abbbf1)

Nous utilisons la méthode drop_duplicates() pour supprimer les lignes en double du DataFrame.

19.	Suppression des lignes avec des données manquantes (NaN) :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/950c8473-8895-4942-b8c5-edd5e29569b2)

Nous utilisons la méthode dropna() pour supprimer les lignes contenant des valeurs manquantes (NaN) dans n'importe quelle colonne du DataFrame.

20.	Réindexation du DataFrame :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/7f6812fb-4466-4184-823c-70ef1c69e79a)

Nous réindexons le DataFrame après avoir effectué les suppressions pour réorganiser les indices de ligne.

21.	Suppression des lignes contenant des valeurs "None" dans n'importe quelle colonne :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/649eecac-1ac2-4508-9d87-920f71b605d4)

Nous utilisons dropna() avec l'argument how='any' pour supprimer les lignes contenant des valeurs "None" dans n'importe quelle colonne du DataFrame.

22.	Correction des valeurs incorrectes dans la colonne "Position" :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ad1c6add-3583-4d3e-b0df-ae881871a0fc)

Nous définissons une fonction correct_position qui tente de convertir la valeur de la colonne "Position" en un nombre entier. Si la conversion échoue (par exemple, si la valeur n'est pas un nombre valide), nous renvoyons None.

23.	Application de la correction à la colonne "Position" :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/252d8624-9d4e-4207-9a86-bb693a74163d)

Nous appliquons la fonction correct_position à la colonne "Position" du DataFrame pour corriger les valeurs incorrectes.

24.	Suppression des données manquantes (NaN) dans la colonne "AcideAmineSauvage" :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d284cd79-e66e-45f0-b36c-aa28efe166b4)

Nous utilisons dropna() pour supprimer les lignes ayant des valeurs manquantes (NaN) dans la colonne "AcideAmineSauvage".

25.	Affichage du DataFrame nettoyé :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d1766efa-956e-43fb-a70f-e640de55cebc)

Nous affichons le DataFrame nettoyé après avoir effectué toutes les étapes de nettoyage.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fb22fb06-4014-4701-8a94-7451dfa23570)

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c8b5cb5e-1187-4a11-a280-11d0033eda58)

--> En combinant ces étapes de nettoyage, la fonction clean_displayed_data(df) assure que le DataFrame résultant, cleaned_df, ne contient que des données valides et cohérentes, ce qui est essentiel pour une analyse précise et fiable.
Le DataFrame contient un total de 2277 lignes, chacune représentant une variation génétique différente avec ses caractéristiques associées


26.	Importer la bibliothèque Pandas pour la manipulation de données :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d40c31eb-10c8-49ac-838f-a30cfdbcfed5)

27.	Définir une fonction display_unique_values qui prend un DataFrame df et une liste de noms de colonnes columns_to_check en tant qu'arguments. Cette fonction affichera les valeurs uniques pour chaque colonne spécifiée.

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/3b7c986e-07c2-46d8-ba67-ccfa0f326afd)

28.	Charger le DataFrame à partir du fichier CSV "displayed_dataframe.csv" :

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/3ca868be-d036-4825-98a5-5d11032645fd)

29.	Sélectionner les colonnes pertinentes que vous souhaitez vérifier pour les valeurs uniques. Dans ce cas, les colonnes "AcideAmineSauvage" et "AcideAmineMute" sont sélectionnées :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/52f63b2b-b115-4c71-961f-2a7446e67caf)

30.	Appeler la fonction display_unique_values avec le DataFrame displayed_df et la liste des colonnes à vérifier :
 
![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b584b975-1a8a-4310-ba7a-35d6ef56d27b)

31.	Importer les bibliothèques nécessaires :

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/bc6194ca-cae0-4b8b-bc63-59ec9d81ff9c)

32.	Charger un DataFrame à partir du fichier "displayed_dataframe.csv" :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c92390ee-0a07-488a-9931-be06b916ad49)

33.	Créer une liste d'acides aminés appelée acides_amines pour une utilisation ultérieure :

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b760d9be-ed91-4521-9661-49d945e29401)

34.	Initialiser une liste vide resultats_filtrations pour stocker les résultats de filtrage :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fa92d799-bac1-4d50-a542-ec0540a3d74b)

35.	Initialiser le widget de sortie output_text pour afficher les résultats :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/8ca36407-8a93-4273-a740-2d4066722c13)

36.	Définir une classe PDF pour la génération de rapports PDF en utilisant la bibliothèque fpdf2 :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/026d2f41-53c4-4af8-8f75-967975736c42)

37.	Définir une fonction generate_pdf pour générer un rapport PDF contenant les résultats de filtration :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/8f303149-37ac-4860-8506-c8f0ddf32366)

38.	Définir une fonction filter_records pour filtrer les enregistrements du DataFrame en fonction de l'acide aminé et de la position :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/6216bde6-eaa3-480d-8e23-0f50e8f0b3d7)

39.	Définir des gestionnaires de clics de bouton (on_continue_button_click et on_stop_button_click) pour traiter les actions de l'utilisateur :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/b2b9cdcd-0932-4982-8eff-0e235a7bdc50)

40.	Créer un lien HTML (link) pour télécharger les résultats sous forme de fichiers CSV :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/39f32e51-5f06-42ba-80c2-3069184cf82c)

41.	Définir une fonction display_results pour afficher les résultats de filtration dans le widget de sortie output_text :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/acc8a2ce-b0f5-4410-b067-0e296fa8f0b0)

42.	Définir une fonction display_widgets pour afficher les widgets interactifs permettant à l'utilisateur de saisir des valeurs d'acides aminés et de position, ainsi qu'un bouton de filtrage :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/451cda1c-19d2-49f7-ae89-372aba80a946)

43.	Appeler la fonction display_widgets pour afficher les widgets interactifs :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/048de45e-9c47-4d98-945f-0a1610ff828c)

44.	Afficher le lien de téléchargement des résultats CSV générés :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/647209c1-d849-48d4-bf1c-cf915a2b30d0)

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/82967cf2-3fe3-4324-a3f7-d75581a0b1e8)

Ce code vous permettra de sélectionner un acide aminé et une position, d'afficher les résultats avec la date et l'heure actuelles, puis de répondre à la question "Voulez-vous continuer ?". Si vous choisissez "Oui", le processus se répétera avec un nouvel acide aminé et une nouvelle position. Si vous choisissez "Non", le code affichera "Exécution terminée." et affichera l'output final de datetime.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ebcfde61-0a0f-41aa-9c6e-b0690a081277)

Ce code affichera tous les résultats de filtrations effectuées depuis le début lorsque vous cliquez sur le bouton "Arrêter". Les résultats de chaque filtration sont stockés dans la liste resultats_filtrations et sont affichés les uns après les autres lorsque le bouton "Arrêter" est cliqué.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/adf66514-c094-42bb-9bbe-00ba8d873857)

# Conclusion

In conclusion, bioinformatics predictive models play a crucial role in evaluating mutations in the BRCA1 and BRCA2 genes. Through a combination of advanced computational techniques and biological data, these models can determine whether mutations are pathogenic or neutral, guide clinical decisions, and facilitate cancer research by leveraging large databases and machine learning methods to improve their accuracy. As such, they have become an important tool in medical genetics, enabling a better understanding of genetic mutations and taking preventive measures to reduce the risk of hereditary cancers.

