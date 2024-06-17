#include <stdio.h>
#include <stdlib.h>

void tampak_depan(){
	printf("====================================================\n");
    printf("=====                                          =====\n");
    printf("=====                 WELCOME                  =====\n");
    printf("=====                   TO                     =====\n");
    printf("=====               BANK JKT 48                =====\n");
    printf("=====                                          =====\n");
    printf("====================================================\n");
    printf("====================================================\n");
    printf("\n");
    printf("\n");
}

int main(){
	int jumlah_uang=1000000,norek,no_rek,pass,transfer,tujuan,nominal,attempts,pilih,keluar;
	system("cls");
	tampak_depan();
no_rek:
	printf(" Masukkan No Rekening Anda : ");
	scanf("%d",&norek);
	if (norek == 1234){
pass:
		printf(" Masukkan PIN Anda : ");
		scanf("%d",&pass);	
		if (pass == 4321){
		
menu:	
		system("cls");
		tampak_depan();
		printf("Menu : \n");
		printf(" 1. Tarik Saldo\n");
		printf(" 2. Transfer Saldo\n");
		printf(" 3. Cek Saldo\n");
		printf(" Pilih : ");
		scanf("%d",&pilih);
		
switch(pilih){
		case 1 :
			system("cls");
			tampak_depan();
		case1:		
				printf(" Pilih Jumlah Saldo Yang Ingin Anda Ambil : \n");
				printf(" 1. Rp. 50.000\n");
				printf(" 2. Rp. 100.000\n");
				printf(" 3. Rp. 150.000\n");
				printf(" 4. Nominal Lain\n\n");
				printf(" Pilih : ");
				scanf("%d",&nominal);
				 if (nominal == 1)
                keluar = 50000;
            else if (nominal == 2)
                keluar = 100000;
            else if (nominal == 3)
                keluar = 150000;
            else if (nominal == 4)
            {
                system("cls");
                tampak_depan();
            inputKeluar:
                printf("Masukan nominal yang ingin anda ambil (kelipatan 50000),\n");
                scanf("%d", &keluar);
                if (keluar % 50000 != 0)
                {
                    system("cls");
                    tampak_depan();
                    printf("Nominal yang anda masukan bukan kelipatan 50000\n\n");
                    goto inputKeluar;
                }
            }
            else
            {
                system("cls");
                tampak_depan();
                printf("Pilihan salah\nSilahkan Pilih kembali\n\n");
                goto case1;
            }
            if (keluar > jumlah_uang)
            {
                system("cls");
                tampak_depan();
                printf("Transaksi Gagal\n");
                printf("Saldo anda tidak mencukupi\n\n");
                
}else{
                system("cls");
                tampak_depan();
                printf("Transaksi Berhasil!\n");
                jumlah_uang = jumlah_uang - keluar;
                printf("Sisa saldo anda,\n%d\n\n", jumlah_uang);
                
}
            break;
				
case 2:
            system("cls");
            tampak_depan();
            printf("Masukan nomor rekening yang anda tuju,\n");
            scanf("%d", &tujuan);
            printf("Masukan nominal yang ingin anda transfer,\n");
            scanf("%d", &transfer);
            if (transfer > jumlah_uang)
            {
                system("cls");
                tampak_depan();
                printf("Transaksi Gagal\n");
                printf("Saldo anda tidak mencukupi\n\n");
                goto konfirmasi;
            }
            else
            {
                system("cls");
                tampak_depan();
                printf("Transaksi Berhasil!\n");
                jumlah_uang = jumlah_uang - transfer;
                printf("Sisa saldo anda,\n%d\n\n", jumlah_uang);
                goto konfirmasi;
            }
            break;
       
 case 3:
            system("cls");
            tampak_depan();
            printf("Saldo anda adalah,\n%d\n\n", jumlah_uang);
            goto konfirmasi;
            break;
        default:
            system("cls");
            printf("Pilihan Menu Salah,\nSilahkan Pilih Kembali\n\n");
            goto menu;
        }
    }
    else
    {
        system("cls");
        tampak_depan();
          attempts++;
            if (attempts <= 3) {
                printf("=====  PIN salah. Silakan coba lagi.           =====\n");
                 goto pass;
            } else {
                printf("=====  PIN salah 3 kali. Kartu Anda telah diblokir.\n");
                return 0;
            }
    }
konfirmasi:
    printf("Apakah anda ingin melakukan transaksi lain ?\n");
    printf("  1. Ya\n");
    printf("  2. Tidak\n");
    printf("Pilih : ");
    scanf("%d", &pilih);
    if (pilih == 1)
        goto menu;
    else if (pilih == 2)
        goto end;
    else
    {
        system("cls");
        tampak_depan();
        printf("Pilihan Salah\nSilahkan pilih kembali\n\n");
        goto konfirmasi;
    }
end:
    system("cls");
    tampak_depan();
    printf("Terimakasih Telah Bertransaksi\n\tDi Bank JKT 48\n\n");
    return 0;	
	   	
				
				
}else{
		 system("cls");
        tampak_depan();
        attempts++;
         if (attempts <= 3) {
                printf("  No Rekening salah. Silakan coba lagi.\n");
                goto no_rek;
            } else {
                printf("  No Rekening salah 3 kali. Kartu Anda telah diblokir.\n");
                return 0;
            }
        
}
}

	

