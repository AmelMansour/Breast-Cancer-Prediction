# Breast-Cancer-Prediction
Modèle de prédiction du cancer du sein 

L'objectif de notre étude est de prédire de manière in silico les mutations affectant les gènes BRCA1 et BRCA2, responsables du cancer du sein, afin d'identifier des motifs similaires associés à des effets délétères. 
En combinant des techniques informatiques sophistiquées et des données biologiques précieuses, cette modèle est en mesure de discerner avec précision si une mutation génétique présente un risque pathogène ou est sans conséquence

Partie bioinformatique

1.	Importation des bibliothèques :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/13585f43-99d0-4f01-8990-48b3d079608e)

Ces lignes importent les bibliothèques nécessaires, notamment pandas pour la manipulation des données et files de Google Colab pour charger et sauvegarder des fichiers.

2.	Chargement des fichiers CSV :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/c8e16dbb-40a9-499c-ad2c-01e6c6b7b61f)

Ces lignes chargent deux fichiers CSV, clinvar_resultBRCA1.csv et clinvar_resultBRCA2.csv, dans deux DataFrames distincts (df1 et df2). Le paramètre sep est utilisé pour spécifier le délimiteur qui sépare les valeurs dans le fichier CSV (dans ce cas, le point-virgule ; est utilisé comme délimiteur).

3.	Concaténation des DataFrames :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ee766178-0e4d-4b91-9149-982cd6f3e645)

Cette ligne concatène les deux DataFrames (df1 et df2) en un seul DataFrame appelé df. L'argument ignore_index=True permet de réinitialiser les index, de sorte que les index du DataFrame résultant sont continus et commencent à partir de zéro.

4.	Sauvegarde du DataFrame dans un fichier CSV :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/fd71eb3a-e3f3-4aff-b2a0-ff24eac4816c)

Ces lignes sauvegardent le DataFrame df dans un fichier CSV nommé BRCA.csv. L'argument index=False indique à pandas de ne pas inclure la colonne d'index dans le fichier CSV final. Le chemin du fichier est spécifié comme '/content/BRCA.csv', et ce chemin peut être utilisé pour accéder au fichier sauvegardé.

5.	Importation des bibliothèques :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/1b5f1af8-e0d5-4ca2-99f4-a579ad9156d9)

Ces lignes importent les bibliothèques nécessaires, notamment pandas pour la manipulation des données et re pour le traitement des expressions régulières.

6.	Fonction load_and_clean_data :
Cette fonction prend deux arguments, input_file (le nom du fichier CSV d'entrée) et output_file (le nom du fichier CSV de sortie).

7.	Chargement du DataFrame :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/522ce24c-6f35-42e7-a2b7-e3c7f8387a81)

Cette ligne charge le DataFrame à partir du fichier CSV d'entrée spécifié par input_file.

8.	Expression régulière pour l'extraction d'informations :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/6f80a7d5-0ede-482d-a88c-33dbc361d778)

r : Le préfixe r devant la chaîne de caractères indique une chaîne brute (raw string) en Python. Cela signifie que les caractères d'échappement comme \ sont traités littéralement et ne sont pas interprétés. C'est couramment utilisé pour les expressions régulières en Python.

\(p\. : Cette partie de l'expression régulière correspond littéralement à la chaîne "(p." dans le texte que vous recherchez. Les parenthèses ( et ) sont des caractères spéciaux en regex, donc pour les inclure littéralement, nous les échappons avec \.

([A-Za-z]+) : Cette partie capture un groupe de lettres majuscules ou minuscules (au moins une lettre) et les enregistre comme un groupe capturant. Les crochets [A-Za-z] définissent une classe de caractères qui correspond à n'importe quelle lettre de l'alphabet, tant en majuscules qu'en minuscules. Le + signifie qu'il doit y avoir au moins une lettre.

(\d+) : Cette partie capture un groupe de chiffres (au moins un chiffre) et les enregistre comme un autre groupe capturant. Le \d correspond à n'importe quel chiffre décimal (0 à 9), et le + signifie qu'il doit y avoir au moins un chiffre.

9.	Application de l'expression régulière et création de nouvelles colonnes :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/97ae1e36-9115-4ee7-bd51-bc95cf8d0c6b)

Cette ligne applique l'expression régulière définie précédemment à la colonne "Name" du DataFrame pour extraire les informations telles que l'acide aminé sauvage, la position et l'acide aminé muté. Ces informations sont stockées dans le DataFrame extracted_info.

10.	Ajout de nouvelles colonnes au DataFrame d'origine :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/0a63ab19-4dfb-4858-a602-6baadf38dcf8)

Ces lignes ajoutent trois nouvelles colonnes au DataFrame d'origine (df) pour stocker les informations extraites : "AcideAmineSauvage", "Position" et "AcideAmineMute".

11.	Sélection des colonnes à afficher :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/d2a10a4d-93b6-4260-b82b-c98bc78fc796)

Ces lignes sélectionnent les colonnes spécifiques du DataFrame d'origine (df) que vous souhaitez afficher et les stockent dans un nouveau DataFrame appelé displayed_df.

12.	Enregistrement du DataFrame affiché dans un fichier CSV de sortie :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/da716d21-7f07-407e-a5e3-2079ffbd73d3)

Cette ligne enregistre le DataFrame displayed_df dans un fichier CSV de sortie spécifié par output_file. L'argument index=False indique de ne pas inclure la colonne d'index dans le fichier CSV final.

13.	Appel de la fonction load_and_clean_data avec les fichiers d'entrée et de sortie spécifiés :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/ca3d93ca-8cf4-4536-93e2-2f0723a3701b)

Ces lignes appellent la fonction load_and_clean_data avec les noms des fichiers d'entrée et de sortie, ce qui effectue toutes les opérations décrites ci-dessus.

14.	Affichage du DataFrame résultant :

 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/0c380fe8-9aff-4a45-b5d6-f5f46355f435)

Cette ligne affiche le DataFrame résultant.

![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/a45d48fd-5dc1-43f9-9077-c8c1530dcc58)

--> Ce résultat correspond à un DataFrame qui a été nettoyé et préparé à partir des données d'origine. Voici ce que signifient les différentes colonnes :
•	Name : Il s'agit du nom de la variation génétique. Il inclut des informations telles que le numéro de version (NM_007294.4 pour BRCA1 et NM_000059.4 pour BRCA2) et la notation de la variation génétique (c.4631C>T).
•	AcideAmineSauvage : Il s'agit de l'acide aminé d'origine avant la mutation génétique. Par exemple, "Pro" signifie la proline.
•	Position : Il s'agit de la position de la mutation dans la séquence génétique. Par exemple, "1544" indique la position 1544.
•	AcideAmineMute : Il s'agit de l'acide aminé résultant de la mutation génétique. Par exemple, "Leu" signifie la leucine.
•	Clinical significance (Last reviewed) : Il s'agit de la signification clinique de la variation génétique telle qu'elle a été examinée pour la dernière fois. Par exemple, "Conflicting interpretations of pathogenicity" signifie qu'il y a des interprétations conflictuelles de la pathogénicité de la variation.
•	GRCh37Location : Il s'agit de la localisation de la variation génétique sur la version GRCh37 du génome humain. Cela donne la position de la variation sur cette version du génome.
•	GRCh38Location : Il s'agit de la localisation de la variation génétique sur la version GRCh38 du génome humain. Cela donne la position de la variation sur cette version du génome.

Le DataFrame contient un total de 3091 lignes (ou "rows") et 7 colonnes, ce qui signifie qu'il y a 3091 entrées distinctes de variations génétiques avec leurs détails associés.
Ce tableau de données est bien préparé pour l'analyse et la visualisation des variations génétiques dans les gènes BRCA1 et BRCA2, en fournissant des informations importantes sur la position, le type de mutation et la signification clinique de chaque variation.


 ![image](https://github.com/AmelMansour/Breast-Cancer-Prediction/assets/141269604/e1cc63b9-36e5-497c-9925-4bada57b0b17)

•	file_path = '/content/displayed_dataframe.csv': Cette ligne de code définit la variable file_path comme une chaîne de caractères contenant le chemin du fichier CSV dans lequel vous souhaitez enregistrer le DataFrame. Le chemin /content/displayed_dataframe.csv indique que le fichier sera enregistré dans le répertoire /content/ avec le nom de fichier displayed_dataframe.csv.
•	displayed_df.to_csv(file_path, index=False): Cette ligne de code utilise la méthode to_csv du DataFrame displayed_df pour enregistrer son contenu dans un fichier CSV. Voici ce que font les arguments passés à cette méthode:
•	file_path: C'est le chemin du fichier CSV où les données seront enregistrées, tel que défini précédemment.
•	index=False: L'argument index est défini sur False, ce qui signifie que l'index du DataFrame (les numéros de ligne) ne sera pas inclus dans le fichier CSV enregistré. Cela est souvent fait lorsque l'index n'a pas de signification particulière et que vous ne souhaitez pas l'inclure dans le fichier CSV final.

15.Importation des bibliothèques :

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

Conclusion

En conclusion, les modèles prédictifs bioinformatiques jouent un rôle crucial dans l’évaluation des mutations des gènes BRCA1 et BRCA2. Grâce à une combinaison de techniques informatiques avancées et de données biologiques, ces modèles peuvent déterminer si les mutations sont pathogènes ou neutres, guider les décisions cliniques et faciliter la recherche sur le cancer, en s'appuyant sur de grandes bases de données et des méthodes d'apprentissage automatique pour améliorer leur précision. À ce titre, ils sont devenus un outil important en génétique médicale, permettant de mieux comprendre les mutations génétiques et de prendre des mesures préventives pour réduire le risque de cancers héréditaires.

