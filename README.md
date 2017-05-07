# JavaTunes-Audio-Player
This is the playback and tag parsing code extracted from my very old JavaTunes project (http://stigc.dk/projects/JavaTunes/). Some of the code is from 2004. I did som quick refatoring to make it usable, I hope I succeded.

Decoders
	Ogg Vorbis, FLAC, MP3, AAC, ALAC and WavPack

Tags supported
	ID3v1, ID3v2, Ogg Comments, APEv2 and QuickTime

Features
	Shourcast, Replay Gain, Gapless playback, lyrics, cover art, multiple artists and genres

Ussage

		File file = new File(...);
		Track track = new TagReaderManager().read(file);
		System.out.println(track.toString());
		
		AudioPlayer audioPlayer = new AudioPlayer();
		AudioInfo ai = audioPlayer.play(track, true, false);
				
		while (true)
		{
			Thread.sleep(1000);	
			synchronized (ai)
			{
				System.out.println(ai.toString());
			}
		}