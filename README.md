# P8-Openclassroom-Billboard-Analysis

Analyse of +60 years of billboard top 100 chart. In case of my personal project in Openclassroom Data Analyst degree.

https://www.billboard.com/charts/hot-100

### BILLBOARD DATAFRAME :

    **url**	: 'http://www.billboard.com/charts/hot-100/' + weekID
    **WeekID** : (m/d/y format) ex: 8/2/1958
    **Week Position** : Actual position at this date (range 100 to 1)
    **Song** : 'One Sweet Day'
    **Performer**	: 'Mariah Carey & Boyz II Men'
    **SongID** : Song + Performer   ex:'One Sweet DayMariah Carey & Boyz II Men	'
    **Instance**	: number of times that this song appear in chart (song can leave the chart for 2 weeks or more and then return )
    **Previous Week Position**	: Previous Week Position obviously but if the osng wasn't inside the chart le the last week then value = NaN
    **Peak Position**	: Top position reached at this date
    **Weeks on Chart**	: total number of occurrence
    **date**	: 1958-08-02	(dtime lib format and data type)
    **year**	: ex: 1958
    **month** : 1 to 12 month
    
    
### ARTISTE DATAFRAME :

    **Performer**	: 'Mariah Carey & Boyz II Men'
    **songs**	: list of song name [ song, song, song, ...]
    **numSong**	: number of differents songs that appears in billboard (len of **songs** column)
    **len_weeks**	: total numbers of occurence in billboard
    **year_min**	: first appearance in billboard
    **year_max**	: last appearance in billboard
    **len_year_different**	: number of differentes years where artist is present in billboard
    **year_space**	: year_max - year_min
    **top1,top5,top10**	: total appearance in top 1/5/10 for the artist
    **is_featuring** : if the artist is actually 2 or more artists (presence of 'Featuring' in Performer column)
    

### SONGS DATAFRAME :

    **SongID** : **Song** + **Performer**   ex:'One Sweet DayMariah Carey & Boyz II Men	'
    **year** : minimum year of this song in the billboard
    **comboWeek**	: maximum of **Weeks on Chart** column
    **comboInstance**	: maximum of **Instance** column
    **maxPose**	: maximum of **Week Position** column
    **top1,top5,top10** : number of top1/5/10 for this song
    
    
### SPOTIFY FEATURES DATAFRAME :
  
  https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/
  
    **SongID**	: **Song** + **Performer**   ex:'One Sweet DayMariah Carey & Boyz II Men	'
    **spotify_genre**	: maybe removing this one and get it with MUSIMAP
    **spotify_track_id** : SPOTIFY TRACK ID
    **spotify_track_explicit**	: maybe removing this one
    **spotify_track_duration_ms**	: duration_ms :The duration of the track in milliseconds.
    **danceability**	: Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, 
                    rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable. 
    **energy**	: Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. 
              Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, 
              while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, 
              perceived loudness, timbre, onset rate, and general entropy. 
    **loudness**	:  The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful 
                 for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological 
                 correlate of physical strength (amplitude). Values typical range between -60 and 0 db. 
    **speechiness**	: Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), 
                  the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words.
                  Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, 
                  including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.
    **acousticness**	: 	A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 
                      1.0 represents high confidence the track is acoustic. 
    **instrumentalness**	: Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. 
                        Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, 
                        the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, 
                        but confidence is higher as the value approaches 1.0. 
    **valence**	: 	A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. 
                Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), 
                while tracks with low valence sound more negative (e.g. sad, depressed, angry). 
    **tempo** :  The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, 
             tempo is the speed or pace of a given piece and derives directly from the average beat duration. 
             The distribution of values for this feature look like this:
  
  
