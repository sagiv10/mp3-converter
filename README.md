# MP3 Converter

A simple tool to convert MP4 media files into MP3 audio files and edit MP3 metadata.  
This is useful for adding files to music servers or updating metadata of existing MP3 files.  

---

## Usage

1. Clone the repository.  

2. Install the script dependencies (see below).  

3. Run the script:  

```bash
sudo /converter.sh full_path_to_input_directory [GENRE]
```


## dependencies

### 1. Linux distribution (or WSL).

### 2. ffmpeg:

```bash
sudo apt install ffmpeg
```

### 3. id3v2:

```bash
sudo apt install id3v2
```


## input structure

Input Structure

The input path should point to a directory named after the artist.
The script should be run separately for each artist.

Inside the artist directory, each album should have its own directory named after the album.
Inside each album directory are the songs in MP4 or MP3 format.

The script supports Hebrew names and spaces in file and folder names.

⚠️ Incorrect input structure may result in undefined behavior.


## genres
the GENRE argument is working like at id3v2, and listed here:
```
0  - Blues
1  - Classic Rock
2  - Country
3  - Dance
4  - Disco
5  - Funk
6  - Grunge
7  - Hip-Hop
8  - Jazz
9  - Metal
10 - New Age
11 - Oldies
12 - Other
13 - Pop
14 - R&B
15 - Rap
16 - Reggae
17 - Rock
18 - Techno
19 - Industrial
20 - Alternative
21 - Ska
22 - Death Metal
23 - Pranks
24 - Soundtrack
25 - Euro-Techno
26 - Ambient
27 - Trip-Hop
28 - Vocal
29 - Jazz+Funk
30 - Fusion
31 - Trance
32 - Classical
33 - Instrumental
34 - Acid
35 - House
36 - Game
37 - Sound Clip
38 - Gospel
39 - Noise
40 - Alternative Rock
41 - Bass
42 - Soul
43 - Punk
44 - Space
45 - Meditative
46 - Instrumental Pop
47 - Instrumental Rock
48 - Ethnic
49 - Gothic
50 - Darkwave
51 - Techno-Industrial
52 - Electronic
53 - Pop-Folk
54 - Eurodance
55 - Dream
56 - Southern Rock
57 - Comedy
58 - Cult
59 - Gangsta
60 - Top 40
61 - Christian Rap
62 - Pop/Funk
63 - Jungle
64 - Native US
65 - Cabaret
66 - New Wave
67 - Psychadelic
68 - Rave
69 - Showtunes
70 - Trailer
71 - Lo-Fi
72 - Tribal
73 - Acid Punk
74 - Acid Jazz
75 - Polka
76 - Retro
77 - Musical
78 - Rock & Roll
79 - Hard Rock
```


## upcoming changes

### Run the script for all artists at once.

### Docker support.
