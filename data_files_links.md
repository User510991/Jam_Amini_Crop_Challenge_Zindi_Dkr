


test

| Description | Nom du fichier | Taille | Lien de t�l�chargement |
| :--- | :--- | :--- | :--- |
| This notebook will get you into the 0.90 scores. We hope you learn from it! | `Multiclass.ipynb` | 286.4 KB | [Multiclass.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Multiclass.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| Slides for the 3rd Zindi/Amini webinar. | `Zindi_webiner_3.pdf` | 953.5 KB | [Zindi_webiner_3.pdf](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Zindi_webiner_3.pdf?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| - | `Fundamentals_of_RS.pdf` | 2.7 MB | [Fundamentals_of_RS.pdf](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Fundamentals_of_RS.pdf?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| - | `introduction_to_remote_sensing.ipynb` | 3.9 MB | [introduction_to_remote_sensing.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/introduction_to_remote_sensing.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| M&M's winning solution. | `Amini_Canopy_or_Crop_Challenge_Solution_Team_M_M.ipynb` | 74.4 KB | [Amini_Canopy_or_Crop_Challenge_Solution_Team_M_M.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Amini_Canopy_or_Crop_Challenge_Solution_Team_M_M.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| Is an example of what your submission file should look like. The order of the rows does not matter, but the names of the "ID" must be correct. | `SampleSubmission.csv` | 218.7 KB | [SampleSubmission.csv](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/SampleSubmission.csv?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| Train contains the target. This is the dataset that you will use to train your model. | `Train.csv` | 1.5 GB | [Train.csv](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Train.csv?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| - | `processing_Earth_Obsersation_Data_for_Machine_Learning.ipynb` | 1.4 MB | [processing_Earth_Obsersation_Data_for_Machine_Learning.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/processing_Earth_Obsersation_Data_for_Machine_Learning.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| - | `Webinar_EO_series.ipynb` | 1.8 MB | [Webinar_EO_series.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Webinar_EO_series.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| Test resembles Train.csv but without the target-related columns. This is the dataset on which you will apply your model to. | `Test.csv` | 664.9 MB | [Test.csv](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/Test.csv?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |
| This is a starter notebook to help you make your first submission. | `StarterNotebook.ipynb` | 111.2 KB | [StarterNotebook.ipynb](https://api.zindi.world/v1/competitions/amini-canopy-or-crop-challenge-september-studyjam/files/StarterNotebook.ipynb?auth_token=zus.v1.Y7Sqww1.QCnzzETg6EdgmB2BvMSS1Kbeagorwf) |



import requests
from pathlib import Path

url = "https://example.com/fichier.zip"
fichier = Path("downloads/fichier.zip")

fichier.parent.mkdir(parents=True, exist_ok=True)

with requests.get(url, stream=True) as response:
    response.raise_for_status()

    with open(fichier, "wb") as f:
        for morceau in response.iter_content(chunk_size=8192):
            if morceau:
                f.write(morceau)

print("Téléchargement terminé :", fichier)
