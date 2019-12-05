#!/bin/bash
a=0
menu=0 
input(){
	let a=$a+1

	echo -n "Nomor nota : "
	read nota[$a]
	echo "=== Data penyewa ==="
	echo -n "Nama 	 : "
	read nama[$a]
	echo -n "No telp	 : "
	read notelp[$a]
	echo -n "Alamat	 : "
	read alamat[$a]
	echo -n "Kode gaun  : "
	read kode[$a]
	echo -n "Warna gaun : "
	read warna[$a]
	echo -n 
	echo "=== Ukuran Gaun ==="
	echo -n "Tinggi badan	(cm)	: "
	read t[$a]
	echo -n "Lebar pundak	(cm)	: "
	read lpu[$a]
	echo -n "Lebar dada  	(cm)	: "
	read ldd[$a]
	echo -n "Lebar pinggang	(cm)	: "
	read lpi[$a]
	echo -n "Lebar lengan	(cm)	: "
	read ll[$a]
	echo -n "Lebar pergelangan	(cm)	: "
	read lpe[$a]
	echo -n 
	echo "=== Harga ==="
	echo -n "Harga sewa /hari	 : Rp. "
	read harga[$a]
	echo -n "Tanggal menyewa : "
	read tanggal[$a]
	echo -n "Total hari menyewa : "
	read hari[$a]
	
	let total[$a]=${harga[$a]}*${hari[$a]}
	echo "Total		 : Rp. ${total[$a]}"
} 
view(){
        for((x=1;x<=a;x++))
        do
		echo "----------------------$x------------------------"
		echo "Nomor nota	: ${nota[$x]}"
		echo "Nama		: ${nama[$x]}"
		echo "No telp		: ${notelp[$x]}"
		echo "Alamat		: ${alamat[$x]}"
		echo "Kode gaun		: ${kode[$x]}"
		echo "Warna gaun	: ${warna[$x]}"
		echo "Tinggi badan	: ${t[$x]}"
		echo "Lebar pundak	: ${lpu[$x]} cm"
		echo "Lebar dada  	: ${ld[$x]} cm"
		echo "Lebar pinggang	: ${lpi[$x]} cm"
		echo "Lebar lengan	: ${ll[$x]} cm"
		echo "Lebar pergelangan	: ${lpe[$x]}"
		echo "Harga sewa /hari	: Rp. ${harga[$x]}"
		echo "Tanggal menyewa	: ${tanggal[$x]}"
		echo "Total hari menyewa: ${hari[$x]}"
		echo "Total		: Rp. ${total[$x]}"
            done
}
search(){
            echo -n "Masukkan nomor nota yang ingin dicari : "
            read cari
            x=0
            y=0
            while [ $x -le $a ] && [ $y == 0 ]
            do
                        let x=$x+1
                        if [ "${nota[x]}" == $cari ]
                        then
                                    y=1
                        fi
            done
}
update(){
	search
	if [ $x -le $a ]
	then
		echo "================================================="
		echo "Nama		: ${nama[$x]}"
		echo "No telp		: ${notelp[$x]}"
		echo "Alamat		: ${alamat[$x]}"
		echo "Kode gaun		: ${kode[$x]}"
		echo "Warna gaun	: ${warna[$x]}"
		echo "Tinggi badan	: ${t[$x]}"
		echo "Lebar pundak	: ${lpu[$x]} cm"
		echo "Lebar dada  	: ${ld[$x]} cm"
		echo "Lebar pinggang	: ${lpi[$x]} cm"
		echo "Lebar lengan	: ${ll[$x]} cm"
		echo "Lebar pergelangan	: ${lpe[$x]}"
		echo "Harga sewa /hari	: Rp. ${harga[$x]}"
		echo "Tanggal menyewa	: ${tanggal[$x]}"
		echo "Total hari menyewa: ${hari[$x]}"
		echo "Total		: Rp. ${total[$x]}"
		echo "================================================="
	echo "=== Data penyewa ==="
	echo -n "Nama 	 : "
	read nama[$a]
	echo -n "No telp	 : "
	read notelp[$a]
	echo -n "Alamat	 : "
	read alamat[$a]
	echo -n "Kode gaun  : "
	read kode[$a]
	echo -n "Warna gaun : "
	read warna[$a]
	echo -n 
	echo "=== Ukuran Gaun ==="
	echo -n "Tinggi badan	(cm)	: "
	read t[$a]
	echo -n "Lebar pundak	(cm)	: "
	read lpu[$a]
	echo -n "Lebar dada  	(cm)	: "
	read ldd[$a]
	echo -n "Lebar pinggang	(cm)	: "
	read lpi[$a]
	echo -n "Lebar lengan	(cm)	: "
	read ll[$a]
	echo -n "Lebar pergelangan	(cm)	: "
	read lpe[$a]
	echo -n 
	echo "=== Harga ==="
	echo -n "Harga sewa /hari	 : Rp. "
	read harga[$a]
	echo -n "Tanggal menyewa : "
	read tanggal[$a]
	echo -n "Total hari menyewa : "
	read hari[$a]
	
	let total[$a]=${harga[$a]}*${hari[$a]}
	echo "Total		 : Rp. ${total[$a]}"
	else
		echo "Data Tidak Ada"
	fi
} 
cetak(){
            search
            if [ $x -le $a ]
            then
                echo "-------------------------------------------"
                echo "Nama		: ${nama[$x]}"
		echo "No telp		: ${notelp[$x]}"
		echo "Alamat		: ${alamat[$x]}"
		echo "Kode gaun		: ${kode[$x]}"
		echo "Warna gaun	: ${warna[$x]}"
		echo "Tinggi badan	: ${t[$x]}"
		echo "Lebar pundak	: ${lpu[$x]} cm"
		echo "Lebar dada  	: ${ld[$x]} cm"
		echo "Lebar pinggang	: ${lpi[$x]} cm"
		echo "Lebar lengan	: ${ll[$x]} cm"
		echo "Lebar pergelangan	: ${lpe[$x]}"
		echo "Harga sewa /hari	: Rp. ${harga[$x]}"
		echo "Tanggal menyewa	: ${tanggal[$x]}"
		echo "Total hari menyewa: ${hari[$x]}"
		echo "Total		: Rp. ${total[$x]}"
                echo "-------------------------------------------"
            else
                        echo "Data Tidak Ada"
            fi
} 
delete(){
search
	if [ $x -gt $a ]
		then
                echo "Data Tidak Ada"
	else
		while [ $x -lt $a ]
		do
		let y=$x+1
		nota[$x]=${nota[$y]}
		nama[$x]=${nama[$y]}
		notelp[$x]=${notelp[$y]}
		alamat[$x]=${alamat[$y]}
		kode[$x]=${kode[$y]}
		warna[$x]=${warna[$y]}
		t[$x]=${t[$y]}
		lpu[$x]=${lpu[$y]}
		ldd[$x]=${ldd[$y]}
		lpi[$x]${lpi[$y]}
		ll[$x]=${ll[$y]}
		lpe[$x]=${lpe[$y]}
		harga[$x]=${harga[$y]}
		tanggal[$x]=${tanggal[$y]}
		hari[$x]=${hari[$y]}
		total[$x]=${total[$y]}
		let x=$x+1
		done
		let a=$a-1
		echo "Data $cari Berhasil Dihapus"
	fi
} 
google(){
	    firefox
}

while [ $menu != 7 ]
do
            echo "======================================================"
            echo "	SELAMAT DATANG DI PROGRAM PERSEWAAN GAUN	"
            echo "======================================================"  
            echo "1.Input"
            echo "2.View"
            echo "3.Update"   
            echo "4.Cetak"
            echo "5.Delete"
            echo "6.Google"
	    echo "7.Exit"
            echo -n "--> Pilih Menu ? "
            read menu
            if [ $menu -eq 1 ]
            then
                        input  
            elif [ $menu -eq 2 ]
            then
            if [ $a -lt 1 ]
 	    then
	    echo "kosong "
	    else
	    view
	    fi
            elif [ $menu -eq 3 ]
            then
                        update
            elif [ $menu -eq 4 ]
            then
                        cetak
            elif [ $menu -eq 5 ]
            then
                        delete
	    elif [ $menu -eq 6 ]
            then
                        google
	    elif [ $menu -eq 7 ]
            then
                        echo "TERIMA KASIH"  
            echo "==================================================="         
            else
                        echo "Salah "
            fi
            echo "	 "
done
