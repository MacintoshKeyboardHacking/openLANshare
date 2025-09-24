some resources I use to share media with an absolute minimum of security, for ease of public access  
  
inside the network, sharing media with DLNA, SMB, and NFS work fine.
  
outside the network SMB and NFS, even FTP have too many firewall and performance issues.  
HTTP(s) and WebDAV seem like the obvious choice, but most media players don't support that!  
(except the *excellent* 'Owlfiles'... shout out!)  

anonymous sftp?  
perhaps the only :practical: wide-area protocol supported by VLC on mobile devices.  
  
    practical because:  
      browsable with VLC's native file picker  
      easy TCP operation, change ports freely to workaround network limitations  
      secure from basic evestropping without requiring certificates  

----  
 
I wanted my 64bit Raspberry Pi4 sftp server to be as performant as possible, so I ./configure'd dropbear with
./configure 'CFLAGS=-O3 -funroll-loops -fomit-frame-pointer -mcpu=cortex-a53'

Dropbear is only used for the ssh authentication/encryption, the '/usr/lib/sftp-server' belonging to openssh is used behind the scenes.
