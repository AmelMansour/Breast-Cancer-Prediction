# Breast-Cancer-Prediction
Modèle de prédiction du cancer du sein 


1.	Importation des bibliothèques :
 
Ces lignes importent les bibliothèques nécessaires, notamment pandas pour la manipulation des données et files de Google Colab pour charger et sauvegarder des fichiers.
2.	Chargement des fichiers CSV :
 
Ces lignes chargent deux fichiers CSV, clinvar_resultBRCA1.csv et clinvar_resultBRCA2.csv, dans deux DataFrames distincts (df1 et df2). Le paramètre sep est utilisé pour spécifier le délimiteur qui sépare les valeurs dans le fichier CSV (dans ce cas, le point-virgule ; est utilisé comme délimiteur).
3.	Concaténation des DataFrames :
 
Cette ligne concatène les deux DataFrames (df1 et df2) en un seul DataFrame appelé df. L'argument ignore_index=True permet de réinitialiser les index, de sorte que les index du DataFrame résultant sont continus et commencent à partir de zéro.
4.	Sauvegarde du DataFrame dans un fichier CSV :
 
Ces lignes sauvegardent le DataFrame df dans un fichier CSV nommé BRCA.csv. L'argument index=False indique à pandas de ne pas inclure la colonne d'index dans le fichier CSV final. Le chemin du fichier est spécifié comme '/content/BRCA.csv', et ce chemin peut être utilisé pour accéder au fichier sauvegardé.

1.	Importation des bibliothèques :
 
Ces lignes importent les bibliothèques nécessaires, notamment pandas pour la manipulation des données et re pour le traitement des expressions régulières.
2.	Fonction load_and_clean_data :
Cette fonction prend deux arguments, input_file (le nom du fichier CSV d'entrée) et output_file (le nom du fichier CSV de sortie).
3.	Chargement du DataFrame :
 
Cette ligne charge le DataFrame à partir du fichier CSV d'entrée spécifié par input_file.
4.	Expression régulière pour l'extraction d'informations :
 
5.	Application de l'expression régulière et création de nouvelles colonnes :
 
Cette ligne applique l'expression régulière définie précédemment à la colonne "Name" du DataFrame pour extraire les informations telles que l'acide aminé sauvage, la position et l'acide aminé muté. Ces informations sont stockées dans le DataFrame extracted_info.
6.	Ajout de nouvelles colonnes au DataFrame d'origine :
 
Ces lignes ajoutent trois nouvelles colonnes au DataFrame d'origine (df) pour stocker les informations extraites : "AcideAmineSauvage", "Position" et "AcideAmineMute".
7.	Sélection des colonnes à afficher :
 
Ces lignes sélectionnent les colonnes spécifiques du DataFrame d'origine (df) que vous souhaitez afficher et les stockent dans un nouveau DataFrame appelé displayed_df.
8.	Enregistrement du DataFrame affiché dans un fichier CSV de sortie :
 
Cette ligne enregistre le DataFrame displayed_df dans un fichier CSV de sortie spécifié par output_file. L'argument index=False indique de ne pas inclure la colonne d'index dans le fichier CSV final.
9.	Appel de la fonction load_and_clean_data avec les fichiers d'entrée et de sortie spécifiés :
 
Ces lignes appellent la fonction load_and_clean_data avec les noms des fichiers d'entrée et de sortie, ce qui effectue toutes les opérations décrites ci-dessus.
10.	Affichage du DataFrame résultant :
 
Cette ligne affiche le DataFrame résultant dans la sortie du bloc-notes Jupyter.



 
•	file_path = '/content/displayed_dataframe.csv': Cette ligne de code définit la variable file_path comme une chaîne de caractères contenant le chemin du fichier CSV dans lequel vous souhaitez enregistrer le DataFrame. Le chemin /content/displayed_dataframe.csv indique que le fichier sera enregistré dans le répertoire /content/ avec le nom de fichier displayed_dataframe.csv.
•	displayed_df.to_csv(file_path, index=False): Cette ligne de code utilise la méthode to_csv du DataFrame displayed_df pour enregistrer son contenu dans un fichier CSV. Voici ce que font les arguments passés à cette méthode:
•	file_path: C'est le chemin du fichier CSV où les données seront enregistrées, tel que défini précédemment.
•	index=False: L'argument index est défini sur False, ce qui signifie que l'index du DataFrame (les numéros de ligne) ne sera pas inclus dans le fichier CSV enregistré. Cela est souvent fait lorsque l'index n'a pas de signification particulière et que vous ne souhaitez pas l'inclure dans le fichier CSV final.

1.	Importation des bibliothèques :
 
Nous importons la bibliothèque Pandas pour la manipulation des données.
2.	Chargement du DataFrame :
 
Nous chargeons un DataFrame à partir d'un fichier CSV appelé 'displayed_dataframe.csv'. Assurez-vous que ce fichier existe dans votre répertoire de travail.
3.	Fonction de nettoyage des données :
 
Nous définissons une fonction appelée clean_displayed_data qui prend en entrée un DataFrame df.
4.	Suppression des lignes en double :
 
Nous utilisons la méthode drop_duplicates() pour supprimer les lignes en double du DataFrame.
5.	Suppression des lignes avec des données manquantes (NaN) :
 
Nous utilisons la méthode dropna() pour supprimer les lignes contenant des valeurs manquantes (NaN) dans n'importe quelle colonne du DataFrame.
6.	Réindexation du DataFrame :
 
Nous réindexons le DataFrame après avoir effectué les suppressions pour réorganiser les indices de ligne.
7.	Suppression des lignes contenant des valeurs "None" dans n'importe quelle colonne :
 
Nous utilisons dropna() avec l'argument how='any' pour supprimer les lignes contenant des valeurs "None" dans n'importe quelle colonne du DataFrame.
8.	Correction des valeurs incorrectes dans la colonne "Position" :
 
Nous définissons une fonction correct_position qui tente de convertir la valeur de la colonne "Position" en un nombre entier. Si la conversion échoue (par exemple, si la valeur n'est pas un nombre valide), nous renvoyons None.
9.	Application de la correction à la colonne "Position" :
 
Nous appliquons la fonction correct_position à la colonne "Position" du DataFrame pour corriger les valeurs incorrectes.
10.	Suppression des données manquantes (NaN) dans la colonne "AcideAmineSauvage" :
 
Nous utilisons dropna() pour supprimer les lignes ayant des valeurs manquantes (NaN) dans la colonne "AcideAmineSauvage".
11.	Affichage du DataFrame nettoyé :
 
Nous affichons le DataFrame nettoyé après avoir effectué toutes les étapes de nettoyage.









1.	Importer la bibliothèque Pandas pour la manipulation de données :
 
2.	Définir une fonction display_unique_values qui prend un DataFrame df et une liste de noms de colonnes columns_to_check en tant qu'arguments. Cette fonction affichera les valeurs uniques pour chaque colonne spécifiée.
 
3.	Charger le DataFrame à partir du fichier CSV "displayed_dataframe.csv" :
 
4.	Sélectionner les colonnes pertinentes que vous souhaitez vérifier pour les valeurs uniques. Dans ce cas, les colonnes "AcideAmineSauvage" et "AcideAmineMute" sont sélectionnées :
 
5.	Appeler la fonction display_unique_values avec le DataFrame displayed_df et la liste des colonnes à vérifier :
 




1.	Importer les bibliothèques nécessaires :
 
2.	Charger un DataFrame à partir du fichier "displayed_dataframe.csv" :
 
3.	Créer une liste d'acides aminés appelée acides_amines pour une utilisation ultérieure :
 
4.	Initialiser une liste vide resultats_filtrations pour stocker les résultats de filtrage :
 
5.	Initialiser le widget de sortie output_text pour afficher les résultats :
 
6.	Définir une classe PDF pour la génération de rapports PDF en utilisant la bibliothèque fpdf2 :
 
7.	Définir une fonction generate_pdf pour générer un rapport PDF contenant les résultats de filtration :
 
8.	Définir une fonction filter_records pour filtrer les enregistrements du DataFrame en fonction de l'acide aminé et de la position :
 
9.	Définir des gestionnaires de clics de bouton (on_continue_button_click et on_stop_button_click) pour traiter les actions de l'utilisateur :
 
10.	Créer un lien HTML (link) pour télécharger les résultats sous forme de fichiers CSV :
 
11.	Définir une fonction display_results pour afficher les résultats de filtration dans le widget de sortie output_text :
 
12.	Définir une fonction display_widgets pour afficher les widgets interactifs permettant à l'utilisateur de saisir des valeurs d'acides aminés et de position, ainsi qu'un bouton de filtrage :
 
13.	Appeler la fonction display_widgets pour afficher les widgets interactifs dans le notebook :
 
14.	Afficher le lien de téléchargement des résultats CSV générés :
 


