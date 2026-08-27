# 🎵 Music Data Visualization — Paisatge emocional i sonor de la música

Projecte d'anàlisi i visualització de dades musicals orientat a explorar com han evolucionat els gèneres, la popularitat i les característiques sonores de la música entre **1990 i 2020**.

El projecte combina dades de **Spotify, Last.fm i Million Song Dataset** per relacionar les característiques acústiques de les cançons amb el seu consum i popularitat.

🎧 **[Explorar el storytelling interactiu](https://public.flourish.studio/story/3529425/)**

## 🎯 Objectiu

L'objectiu és transformar un conjunt de dades musicals complex en una història visual que permeti explorar l'evolució del consum i de les característiques de la música.

Algunes de les preguntes analitzades són:

- Quins gèneres musicals han guanyat o perdut presència al llarg del temps?
- Han canviat els patrons de popularitat segons l'any de publicació?
- Les cançons més populars comparteixen característiques sonores?
- Quin gènere té més cançons amb alta popularitat relativa?
- Quin és el paisatge emocional de la música consumida?

## 📊 Dades

El projecte utilitza el conjunt de dades **Million Song Dataset + Spotify + Last.fm**, disponible a Kaggle.

Les dues fonts principals utilitzades són:

- `Music_Info.csv` — metadades i característiques sonores de **50.683 pistes**.
- `User_Listening_History.csv` — més de **9,7 milions de registres d'escolta** d'usuaris.

Els dos conjunts de dades s'integren mitjançant `track_id` per relacionar les característiques de cada cançó amb el seu volum d'escoltes.

> ℹ️ `User_Listening_History.csv` no s'inclou al repositori a causa de la seva mida. Es pot obtenir des del dataset original de Kaggle.

**Font de les dades:**  
[Million Song Dataset + Spotify + Last.fm — Kaggle](https://www.kaggle.com/datasets/undefinenull/million-song-dataset-spotify-lastfm/data)

## 🔎 Metodologia

El projecte segueix un procés complet de preparació i visualització de dades:

1. **Càrrega i exploració de les dades**
2. **Integració de les fonts mitjançant `track_id`**
3. **Neteja i tractament de valors incoherents o absents**
4. **Preparació i transformació de variables**
5. **Creació de noves característiques**
6. **Anàlisi exploratòria**
7. **Generació de datasets específics per a les visualitzacions**
8. **Construcció del storytelling interactiu amb Flourish**

Després de la integració i preparació de les dades, s'obté un conjunt de **30.459 registres** amb informació sobre característiques sonores, gèneres, metadades i nombre total d'escoltes.

## ⚙️ Feature engineering

A partir de les variables originals es creen noves característiques per facilitar l'anàlisi:

- `total_plays` — nombre total de reproduccions per cançó.
- `duration_min` — durada de la cançó en minuts.
- `popularity_norm` — índex normalitzat de popularitat.
- `mood` — índex emocional derivat de `energy` i `valence`.
- `genre_grouped` — agrupació dels gèneres en categories més generals.
- `tempo_class` — classificació del tempo en `Slow`, `Medium` i `Fast`.

També es treballa amb variables acústiques com `danceability`, `energy`, `valence`, `tempo`, `acousticness`, `instrumentalness` i `loudness`.

## 📈 Visualització i storytelling

Per comunicar els resultats es generen diferents datasets adaptats a les visualitzacions i es construeix un **storytelling interactiu amb Flourish**.

El resultat permet explorar visualment l'evolució dels gèneres, la popularitat de les cançons i la relació entre les seves característiques sonores i emocionals.

🎧 **[Veure la visualització interactiva](https://public.flourish.studio/story/3529425/)**

## 🛠️ Tecnologies utilitzades

- **R**
- **R Markdown**
- **dplyr / tidyverse**
- **Anàlisi exploratòria de dades**
- **Transformació i preparació de dades**
- **Flourish**
- **Git / GitHub**

## 📁 Estructura del repositori

- `rstudio/music_analysis.Rmd` — codi de preparació, neteja, transformació i anàlisi de les dades.
- `rstudio/Music_Info.csv` — metadades i característiques musicals.
- `rstudio/data_clean.csv` — conjunt de dades resultant del procés de preparació.
- `rstudio/music_scatter.csv` — dades preparades per a visualitzacions de relacions entre variables.
- `rstudio/music_year.csv` — dades preparades per a l'anàlisi temporal.
- `rstudio/music_race.csv` — dades derivades per a la visualització de l'evolució musical.
- `rstudio/top10_tracks_radar.csv` — dades de les cançons seleccionades per a la comparació de característiques.
- `rstudio/high_popularity_by_genre.csv` i `high_popularity_by_genre2.csv` — dades derivades per analitzar la popularitat per gènere.
- `.gitignore` — exclou del repositori el dataset d'historial d'escoltes pel seu volum.


---

📌 Projecte desenvolupat com a part del **Màster Universitari en Ciència de Dades de la Universitat Oberta de Catalunya (UOC)**.


