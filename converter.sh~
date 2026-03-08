#!/bin/bash

INPUT_DIR=$1
OUTPUT_DIR="${INPUT_DIR}_converted"
ARTIST_NAME="${INPUT_DIR##*/}"

GENRE=$2

MP4_MIME="video/mp4"
MP3_MIME="audio/mpeg"

mkdir "${OUTPUT_DIR}"

for album_path in "${INPUT_DIR}"/*; do
    if [ -d "$album_path" ]; then

	ALBUM_NAME=${album_path##*/}
	ALBUM_OUTPUT_DIR="${OUTPUT_DIR}/${ALBUM_NAME}"
	mkdir "${ALBUM_OUTPUT_DIR}"
	
	for song_path in "${INPUT_DIR}/${ALBUM_NAME}"/*; do
            if [ -f "$song_path" ]; then 
	
		
		SONG_NAME=${song_path##*/}
		SONG_NAME=${SONG_NAME%.*}

		mime=$(file --mime-type -b "$song_path")
		
		if [[ "$mime" == "$MP4_MIME" ]]; then

		    ffmpeg -i "${song_path}" -q:a 0 -map a "${ALBUM_OUTPUT_DIR}/${SONG_NAME}.mp3"

		fi
	    
	    	if [[ "$mime" == "$MP3_MIME" ]]; then

		    cp "${song_path}" "${ALBUM_OUTPUT_DIR}/${SONG_NAME}.mp3"

                fi
	    fi
	done

	track_number=1	
	album_num_songs=$("find ${ALBUM_OUTPUT_DIR} -type f | wc -l")

	for output_song_path in "${ALBUM_OUTPUT_DIR}"/*; do

		    
		id3v2 --song "${SONG_NAME}" --artist "${ARTIST_NAME}" --album "${ALBUM_NAME}" --track "${track_number}/${album_num_songs}" --genre 1  --year 1948 "${output_song_path}"

	    ((track_number++))

	done

    fi
done

#rm -fr ${OUTPUT_DIR}

