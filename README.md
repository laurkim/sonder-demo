# Sonder
![Sonder-Splash](demo-material/sonder-splash.png)

## Description
This is a demo for Sonder, an application built upon a React/Redux front end and Ruby on Rails back end. Sonder uses OAuth2 to verify a user's real Spotify account and then compiles and analyzes the user's listening history. With the user's account data, Sonder will then render the user's top played tracks, create a new playlist that persists to their Spotify account for tracks the user may like based on their listening habits, and upon form submission the application will create a personality analysis based on user input and Spotify listening patterns.

If the demo gifs are running at a slower speed, please reference the similarly named files inside the directory labeled *demo-material*. 

## Core Features
1. [OAuth2 Login with Spotify](#oauth2-login-with-spotify)
2. [Embedded Spotify Player](#embedded-spotify-player)
3. [Spotify Playlist Creation](#spotify-playlist-creation)
4. [Provide User Listening Habits](#provide-user-listening-habits)
5. [User Personality Analysis](#user-personality-analysis)
6. [Big Five Personality Attributes](#big-five-personality-attributes)
7. [Deep Level Personality Breakdown](#deep-level-personality-breakdown)
8. [Dynamic Routing](#dynamic-routing)
9. [User Logout](#user-logout)

### OAuth2 Login with Spotify
On the splash page, there is a button that will direct a user to login with their Spotify or Facebook. Through Spotify's OAuth2 process, a user will be authenticated and authorized and redirected a page that will request final confirmation to connect the Sonder app to the user's Spotify account. Once confirmed, the application will redirect to the home page.

![Sonder-Login](demo-material/sonder-login.gif)

### Embedded Spotify Player
On the home page, a button to toggle a sidebar menu appears on the lefthand side of the webpage. When clicked, it will bring in the menu as an overlay to the entire webpage and display an embedded Spotify playlist. The menu can be retracted by clicking anywhere outside of the sidebar. The embedded playlist includes the functionality to play all songs in the playlist in their entirety, not just a sample snippet of the song.

![Sonder-Embedded-Playlist](demo-material/sonder-embedded-playlist.gif)

### Spotify Playlist Creation
Sonder will generate a new playlist for a user based on their listening patterns. It will compile a user's top played tracks and, based on certain track attributes such as modality and valence, a new playlist of recommended tracks will be created and persist to the user's account.

![Sonder-Recommended-Playlist](demo-material/sonder-recommended-playlist.gif)

### Provide User Listening Habits
Sonder will provide a list of the user's top played tracks. In the rendering of each track, attributes for each track will be provided in percentages. Each track has an analysis for the percentage of acousticness, danceability, energy, modality, vocal content, and valence. The track title, track artist, and track cover album will be provided as well. The is compiled in a descending order, meaning the first track listed will be the user's top played track.

![Sonder-Top-Tracks](demo-material/sonder-top-tracks.gif)

### User Personality Analysis
A form renders at the top of the webpage which asks a user for input in regards to their preferred type of music. This input takes into account a user's tonality in the way they write, so the more input that is provided, the more accurate the personality analysis. This input, along with the analysis of the user's listening habits, are included into a call to the Watson API to provide a personality analysis. Upon form submission, the webpage will dynamically render the profile breakdown in a chart alongside the user's top played tracks.

![Sonder-Personality-Form](demo-material/sonder-personality-form.gif)

### Big Five Personality Attributes
The personality analysis is comprised of five main components:

1. Openness

   Openness demonstrates an appreciation for art, emotion, adventure, unusual ideas, curiosity, and variety of experience. Openness reflects the degree of intellectual curiosity, creativity and a preference for novelty and variety a person has. It is also described as the extent to which a person is imaginative or independent and depicts a personal preference for a variety of activities over a strict routine. High openness can be perceived as unpredictability or lack of focus, and more likely to engage in risky behavior.

2. Conscientiousness

   Conscientiousness demonstrates a tendency to be organized and dependable, show self-discipline, act dutifully, aim for achievement, and prefer planned rather than spontaneous behavior. High conscientiousness is often perceived as stubbornness and obsession. Low conscientiousness is associated with flexibility and spontaneity, but can also appear as sloppiness and lack of reliability.

3. Extraversion

   Extraversion has characteristics of energy, positive emotions, assertiveness, sociability and the tendency to seek stimulation in the company of others, and talkativeness. High extraversion is often perceived as attention-seeking, and domineering. Low extraversion causes a reserved, reflective personality, which can be perceived as aloof or self-absorbed.

4. Agreeableness

   Agreeableness demonstrates a tendency to be compassionate and cooperative rather than suspicious and antagonistic towards others. It is also a measure of one's trusting and helpful nature, and whether a person is generally well-tempered or not. High agreeableness is often seen as naive or submissive. Low agreeableness personalities are often competitive or challenging people, which can be seen as argumentativeness or untrustworthiness.

5. Neuroticism

   Neuroticism is the tendency to experience unpleasant emotions easily, such as anger, anxiety, depression, and vulnerability. Neuroticism also refers to the degree of emotional stability and impulse control and is sometimes referred to by its low pole, 'emotional stability'. A high need for stability manifests itself as a stable and calm personality, but can be seen as uninspiring and unconcerned. A low need for stability causes a reactive and excitable personality, often very dynamic individuals, but they can be perceived as unstable or insecure.

These components, most often referred to as the Big Five, are presented in a radar chart with each endpoint on the pentagon standing for one of the five personality traits. Each of these are provided as a numerical score, to symbolize the percentage in which this attribute is present in the user. For example, in the below demo, the user's personality trait for Openness is at 82, meaning out of a 100%, the user's openness is at 82%.

![Sonder-Big-Five-Personality](demo-material/sonder-big-five-personality.gif)

### Deep Level Personality Breakdown
Each of the Big Five personality traits is comprised of various attributes. When a user clicks on one of the five buttons below the radar chart, it will trigger a render of the sub-attributes for each of the main personality traits and display it in a doughnut chart.

Similar to the rendering of the Big Five personality traits, each of the attributes are provided as percentages.

![Sonder-Attribute-Breakdown](demo-material/sonder-attribute-breakdown.gif)

### Dynamic Routing
A navigation bar at the top of the page provides links to the Home page, About page, as well as the logout functionality.

A user can click the "About" on the navigation bar to be redirected to a different URL and render the About page. This page gives a detailed description of the Big Five Personality Traits as well as the subcategories for each.

Once finished, a user can click the "Home" button on the navigation bar to return to the main page which renders the user's listening history and the form to retrieve the user's personality traits.

![Sonder-About](demo-material/sonder-about.gif)

### User Logout
When a user wishes to exit the application, the logout button in the navigation bar will redirect the application to the Splash page, where a new user will be can login and get a personality analysis based on their separate listening habits.

![Sonder-Logout](demo-material/sonder-logout.gif)
