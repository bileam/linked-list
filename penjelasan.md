pengertian linked list
=secara toeri, linket list adalah sejumlah node yang di hubangkan secara linear dengan bantuan pointer.
=untuk implementasi linket list, kita harus memahasi struct dan pointer terlebaih dahulu.
=penggunaan struct memungkinkan kita bekerja dengan satu record yang memiliki banyak field.

Dalam linket alokasi memori dinamis
-memesan memori secara konvensional misalnya char s[10000],namun sayangnya,kita akan kehilangn kebebasan untuk mendiolokasikan memory yang sudah tidak terpakai
-pengelokasikan memori secara dinamis dapat di lakukan dengan salah satu fungsi alokasi memory yaitu melloc().
-sementara lawannya, deolokasi memory, dapat di lakukan dengan memanggil fungsi free().

tahap-tahap yang singkat untuk mendeklasikan fungsi malloc dan free
1.mendeklasikan struct terlebih dahulu
2.kita memasang memori secara dinamis yag akan di gunakan oleh struct tersebut.
3.apa bila sebelumnya kita menggunakan notasi titip untuk mengakses feald,makan dalam pengalokasian dinamis ini, kita menggunakan notasi(->)

