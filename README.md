for($i=1;$i<=9;$i++)
{
	open(my $fh, '>', 'conf.txt');
	@data="receptor = pfcrt.pdbqt \nligand =c".$i.".pdbqt\ncenter_x=2.727\ncenter_y=-0.551\ncenter_z=22.2

size_x=74
size_y=76
size_z=64 ";
	print $fh @data;
	close $fh;
    $log="log".$i.".txt";
    @args = ("vina --config conf.txt --log ".$log);
	system(@args);
}
print "done\n";
