---
layout: post
title: Bloc Jams
thumbnail-path: "img/blocjams.png"
short-description: Bloc Jams is a Front-end online music player
 #BlocFlix is a Netflix replica for finding the best movies and watching them online.

---
{:.center}
![]({{ site.baseurl }}/img/blocjams.png)

## Explanation

Bloc Jams is the front-end design of a music player. It was my first attempt at creating something putting together Javascript, HTML, and CSS. It includes a full functioning volume, track position controls and track selections. It also includes click and mouse-over/ hover functions.

## Problem

The project started as a vanilla JavascriptDOM and the task was to refactor the site and add functioning, such as next/previous buttons on the player bar, using Jquery.

## Solution
>Ex: In this block of code is get the previous song number by calling a function (again, not shown here cause this is getting really long.) Note that we return index zero (the first song) if the current song is equal to the length of the album (this way the next song is the first song and the next button wraps around.) Next using another function we get the index value of the current song and then increment it by one (again if the index is larger than the length of the album we reset the value to zero - the first track.) We then set the song, (note that this function uses actual track listing numbers rather than the array index so we need to increment this value by one to account for the 0/1 first tack shift,) and then we play the song.

{%highlight javascript%}
var nextSong = function() {
var getLastSongNumber = function(index){
    return index == 0 ? currentAlbum.songs.length : index;
}
var currentSongIndex = trackIndex(currentAlbum, currentSongFromAlbum);
    currentSongIndex++;
    if (currentSongIndex >= currentAlbum.songs.length){
        currentSongIndex = 0;
}
setSong(currentSongIndex + 1);
currentSoundFile.play();
updateSeekBarWhileSongPlays();
updatePlayerBarSong();

var lastSongNumber = getLastSongNumber(currentSongIndex);
var $nextSongNumberCell = getSongNumberCell(currentlyPlayingSongNumber);
var $lastSongNumberCell = getSongNumberCell(lastSongNumber)

var $volumeFill = $('.volume .fill');
var $volumeThumb = $('.volume .thumb')
$volumeFill.width(currentVolume + '%');
$volumeThumb.css({left: currentVolume + '%'});
$nextSongNumberCell.html(pauseButtonTemplate);
$lastSongNumberCell.html(lastSongNumber);
};
{%endhighlight%}

## Results

Converting DOM code to Jquery added functionality to the music player. Shortening the lines of code in functions made it more readable and easy to understand.

## Conclusion

There is more steps and then I have include on this blog and this project was my first task at converting DOM to Jquery. This was also my first time attempting to work with all three major front-end languages (HTML, CSS and Javascript).
