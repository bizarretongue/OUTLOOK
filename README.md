@echo off
title BACKUP\RESTAURE MICROSOFT OUTLOOK (Ver. 1.5) 2017  -  Desenvolvido por Marcelo Oliveira©  -  marcelo.infor@gmail.com 
mode 120,20

## ATRIBUIDO O COMANDO PELA VARIAVEL xcopy
set xcopy=xcopy /h /s /v /-y /j /w

## ATRIBUIDO TODAS AS UNIDADES POR VARIAVEIS
set dd=d:\
set ee=e:\
set ff=f:\
set gg=g:\
set hh=h:\
set ii=i:\
set jj=j:\
set kk=k:\
set ll=l:\
set mm=m:\
set nn=n:\
set oo=o:\
set pp=p:\
set qq=q:\
set rr=r:\
set ss=ss:\
set tt=t:\
set uu=u:\
set vv=v:\
set xx=x:\
set ww=w:\
set yy=y:\
set zz=z:\


:menu
cls
echo.
echo                      MENU PRINCIPAL DO MICROSOFT OUTLOOK
echo  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo  º 1. MENU - FAZER BACKUPS DO OUTLOOK                                    º 
echo  º 2. MENU - RESTAURAR BACKUP DO OUTLOOK                                 º
echo  º 3. MENU - SALVAR REGISTRO DE PERFIL DO OUTLOOK                        º
echo  º 4. Sair                                                               º
echo  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
set /p menu= Escolha uma opcao acima (Exemplo 1 ou 2): 

if %menu% equ 1 goto menu1
if %menu% equ 2 goto menu2
if %menu% equ 3 goto menu3
if %menu% equ 4 goto sair
if %menu% geq 5 goto invalida
if %menu% equ 0 goto invalida


:menu1
cls
echo.
echo     MENU DE BACKUP DO MICROSOFT OUTLOOK 2003/2007/2010/2013/2016
echo  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo  º 0. Voltar ao MENU                                                     º
echo  º 1. Salvar Pasta Outlook\Local                                         º
echo  º 2. Salvar Pasta Outlook\Roaming                                       º
echo  º 3. Salvar Pasta Assinaturas\Dicionario\Modelos\Papel de Carta         º
echo  º 4. Salvar Pasta PST no Windows XP (EM TESTE)                          º
echo  º 5. Sair                                                               º
echo  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
set /p menu1= Escolha uma opcao acima (Exemplo 1 ou 2): 

if %menu1% equ 1 goto backup1
if %menu1% equ 2 goto backup2
if %menu1% equ 3 goto backup4
if %menu1% equ 4 goto backup3
if %menu1% equ 5 goto sair
if %menu1% geq 6 goto invalida1
if %menu1% equ 0 goto menu


:menu2
cls
echo.
echo     MENU DE RESTAURACAO DO MICROSOFT OUTLOOK 2003/2007/2010/2013/2016
echo  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo  º 0. Voltar ao MENU                                                     º 
echo  º 1. Restaurar Pasta Outlook\Local                                      º
echo  º 2. Restaurar Pasta Outlook\Roaming                                    º
echo  º 3. Restaurar Pasta Assinaturas\Dicionario\Modelos\Papel de Carta      º
echo  º 4. Restaurar Pasta PST para Windows XP (EM TESTE)                     º
echo  º 5. Sair                                                               º
echo  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
set /p menu2= Escolha uma opcao acima (Exemplo 1 ou 2): 

if %menu2% equ 1 goto restaurar1
if %menu2% equ 2 goto restaurar2
if %menu2% equ 3 goto restaurar4
if %menu2% equ 4 goto restaurar3
if %menu2% equ 5 goto sair
if %menu2% geq 6 goto invalida2
if %menu2% equ 0 goto menu


:menu3
cls
echo.
echo    MENU - SALVAR PERFIL DE REGISTRO DO OUTLOOK 2003/2007/2010/2013/2016
echo  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo  º 0. Voltar ao MENU                                                     º 
echo  º 1. Salvar Perfil de Registro do Office 2003 ?                         º
echo  º 2. Salvar Perfil de Registro do Office 2007 ?                         º
echo  º 3. Salvar Perfil de Registro do Office 2010 ?                         º
echo  º 4. Salvar Perfil de Registro do Office 2013 ?                         º
echo  º 5. Salvar Perfil de Registro do Office 2016 ?                         º
echo  º 6. Salvar Perfil de Registro do Office Outlook (Todas Versoes)        º
echo  º 7. Sair                                                               º
echo  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
set /p menu3= Escolha uma opcao acima (Exemplo 1 ou 2): 

if %menu3% equ 1 goto perfil1
if %menu3% equ 2 goto perfil2
if %menu3% equ 3 goto perfil3
if %menu3% equ 4 goto perfil4
if %menu3% equ 5 goto perfil5
if %menu3% equ 6 goto perfil6
if %menu3% equ 7 goto sair
if %menu3% geq 8 goto invalida3
if %menu3% equ 0 goto menu

##########################################################################################################
##########################################################################################################

:backup1
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Copiando arquivos Outlook da pasta LOCAL em Outlook\Outlook-local                        º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo                                                        OBS: Digite zero (0) para VOLTAR!
echo.
set /p unidade= Escolha a unidade onde sera salvo o backup (Exemplo C, D, E ou F) - OBS (em minusculas):
echo.

if %unidade% equ 0 goto voltar1
if %unidade% equ c goto unidadec
if %unidade% equ d goto unidaded
if %unidade% equ e goto unidadee
if %unidade% equ f goto unidadef
if %unidade% equ g goto unidadeg
if %unidade% equ h goto unidadeh
if %unidade% equ i goto unidadei
if %unidade% equ j goto unidadej
if %unidade% equ k goto unidadek
if %unidade% equ l goto unidadel
if %unidade% equ m goto unidadem
if %unidade% equ n goto unidaden
if %unidade% equ o goto unidadeo
if %unidade% equ p goto unidadep
if %unidade% equ q goto unidadeq
if %unidade% equ r goto unidader
if %unidade% equ s goto unidades
if %unidade% equ t goto unidadet
if %unidade% equ u goto unidadeu
if %unidade% equ v goto unidadev
if %unidade% equ x goto unidadex
if %unidade% equ y goto unidadey
if %unidade% equ w goto unidadew
if %unidade% equ z goto unidadez
if %unidade% geq 1 goto invuni1



:unidadec
cls
echo.
echo OBS: Ao selecionar essa Unidade "C" o backup sera salvo na Area de Trabalho. 
md %USERPROFILE%\Desktop\Outlook\
md %USERPROFILE%\Desktop\Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %USERPROFILE%\Desktop\Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %USERPROFILE%\Desktop\Outlook\Outlook-Local\
rd %USERPROFILE%\Desktop\Outlook\
cls
set uni=C
goto local

:unidaded
cls
echo OBS: Ao selecionar essa Unidade "D" o backup sera salvo na Raiz da Unidade.
md %dd%Outlook\
md %dd%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %dd%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %dd%Outlook\Outlook-Local\
rd %dd%Outlook\
cls
set uni=D
goto local

:unidadee
cls
echo OBS: Ao selecionar essa Unidade "E" o backup sera salvo na Raiz da Unidade.
md %ee%Outlook\
md %ee%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ee%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ee%Outlook\Outlook-Local\
rd %ee%Outlook\
cls
set uni=E
goto local

:unidadef
cls
echo OBS: Ao selecionar essa Unidade "F" o backup sera salvo na Raiz da Unidade.
md %ff%Outlook\
md %ff%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ff%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ff%Outlook\Outlook-Local\
rd %ff%Outlook\
cls
set uni=F
goto local

:unidadeg
cls
echo OBS: Ao selecionar essa Unidade "G" o backup sera salvo na Raiz da Unidade.
md %gg%Outlook\
md %gg%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %gg%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %gg%Outlook\Outlook-Local\
rd %gg%Outlook\
cls
set uni=G
goto local

:unidadeh
cls
echo OBS: Ao selecionar essa Unidade "H" o backup sera salvo na Raiz da Unidade.
md %hh%Outlook\
md %hh%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %hh%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %hh%Outlook\Outlook-Local\
rd %hh%Outlook\
cls
set uni=H
goto local

:unidadei
cls
echo OBS: Ao selecionar essa Unidade "I" o backup sera salvo na Raiz da Unidade.
md %ii%Outlook\
md %ii%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ii%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ii%Outlook\Outlook-Local\
rd %ii%Outlook\
cls
set uni=I
goto local

:unidadej
cls
echo OBS: Ao selecionar essa Unidade "J" o backup sera salvo na Raiz da Unidade.
md %jj%Outlook\
md %jj%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %jj%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %jj%Outlook\Outlook-Local\
rd %jj%Outlook\
cls
set uni=J
goto local

:unidadel
cls
echo OBS: Ao selecionar essa Unidade "L" o backup sera salvo na Raiz da Unidade.
md %ll%Outlook\
md %ll%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ll%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ll%Outlook\Outlook-Local\
rd %ll%Outlook\
cls
set uni=J
goto local

:unidadem
cls
echo OBS: Ao selecionar essa Unidade "M" o backup sera salvo na Raiz da Unidade.
md %mm%Outlook\
md %mm%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %mm%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %mm%Outlook\Outlook-Local\
rd %mm%Outlook\
cls
set uni=M
goto local

:unidaden
cls
echo OBS: Ao selecionar essa Unidade "N" o backup sera salvo na Raiz da Unidade.
md %nn%Outlook\
md %nn%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %nn%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %nn%Outlook\Outlook-Local\
rd %nn%Outlook\
cls
set uni=N
goto local

:unidadeo
cls
echo OBS: Ao selecionar essa Unidade "O" o backup sera salvo na Raiz da Unidade.
md %oo%Outlook\
md %oo%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %oo%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %oo%Outlook\Outlook-Local\
rd %oo%Outlook\
cls
set uni=O
goto local

:unidadep
cls
echo OBS: Ao selecionar essa Unidade "P" o backup sera salvo na Raiz da Unidade.
md %pp%Outlook\
md %pp%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %pp%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %pp%Outlook\Outlook-Local\
rd %pp%Outlook\
cls
set uni=P
goto local

:unidadeq
cls
echo OBS: Ao selecionar essa Unidade "Q" o backup sera salvo na Raiz da Unidade.
md %qq%Outlook\
md %qq%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %qq%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %qq%Outlook\Outlook-Local\
rd %qq%Outlook\
cls
set uni=Q
goto local

:unidader
cls
echo OBS: Ao selecionar essa Unidade "R" o backup sera salvo na Raiz da Unidade.
md %rr%Outlook\
md %rr%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %rr%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %rr%Outlook\Outlook-Local\
rd %rr%Outlook\
cls
set uni=R
goto local

:unidades
cls
echo OBS: Ao selecionar essa Unidade "S" o backup sera salvo na Raiz da Unidade.
md %ss%Outlook\
md %ss%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ss%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ss%Outlook\Outlook-Local\
rd %ss%Outlook\
cls
set uni=S
goto local

:unidadet
cls
echo OBS: Ao selecionar essa Unidade "T" o backup sera salvo na Raiz da Unidade.
md %tt%Outlook\
md %tt%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %tt%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %tt%Outlook\Outlook-Local\
rd %tt%Outlook\
cls
set uni=T
goto local

:unidadeu
cls
echo OBS: Ao selecionar essa Unidade "U" o backup sera salvo na Raiz da Unidade.
md %uu%Outlook\
md %uu%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %uu%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %uu%Outlook\Outlook-Local\
rd %uu%Outlook\
cls
set uni=U
goto local

:unidadev
cls
echo OBS: Ao selecionar essa Unidade "V" o backup sera salvo na Raiz da Unidade.
md %vv%Outlook\
md %vv%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %vv%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %vv%Outlook\Outlook-Local\
rd %v%Outlook\
cls
set uni=V
goto local

:unidadex
cls
echo OBS: Ao selecionar essa Unidade "X" o backup sera salvo na Raiz da Unidade.
md %xx%Outlook\
md %xx%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %xx%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %xx%Outlook\Outlook-Local\
rd %xx%Outlook\
cls
set uni=X
goto local

:unidadew
cls
echo OBS: Ao selecionar essa Unidade "W" o backup sera salvo na Raiz da Unidade.
md %ww%Outlook\
md %ww%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %ww%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ww%Outlook\Outlook-Local\
rd %ww%Outlook\
cls
set uni=W
goto local

:unidadey
cls
echo OBS: Ao selecionar essa Unidade "Y" o backup sera salvo na Raiz da Unidade.
md %yy%Outlook\
md %yy%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %yy%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %yy%Outlook\Outlook-Local\
rd %yy%Outlook\
cls
set uni=Y
goto local

:unidadez
cls
echo OBS: Ao selecionar essa Unidade "Z" o backup sera salvo na Raiz da Unidade.
md %zz%Outlook\
md %zz%Outlook\Outlook-Local\
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Local\Microsoft\outlook\*.* %zz%Outlook\Outlook-local
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %zz%Outlook\Outlook-Local\
rd %zz%Outlook\
cls
set uni=Z
goto local


:local
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Backup da pasta LOCAL na %uni% em Outlook\Outlook-local                    º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE BACKUP
pause > nul
goto menu1

##########################################################################################################
##########################################################################################################

:backup2
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Copiando arquivos Outlook da pasta ROAMING para Area de Trabalho Outlook\Outlook-Roaming     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
set /p unidade1= Escolha a unidade onde sera salvo o backup (Exemplo C, D, E ou F) - OBS (em minusculas):

if %unidade1% equ 0 goto voltar2
if %unidade1% equ c goto unidade1c
if %unidade1% equ d goto unidade1d
if %unidade1% equ e goto unidade1e
if %unidade1% equ f goto unidade1f
if %unidade1% equ g goto unidade1g
if %unidade1% equ h goto unidade1h
if %unidade1% equ i goto unidade1i
if %unidade1% equ j goto unidade1j
if %unidade1% equ k goto unidade1k
if %unidade1% equ l goto unidade1l
if %unidade1% equ m goto unidade1m
if %unidade1% equ n goto unidade1n
if %unidade1% equ o goto unidade1o
if %unidade1% equ p goto unidade1p
if %unidade1% equ q goto unidade1q
if %unidade1% equ r goto unidade1r
if %unidade1% equ s goto unidade1s
if %unidade1% equ t goto unidade1t
if %unidade1% equ u goto unidade1u
if %unidade1% equ v goto unidade1v
if %unidade1% equ x goto unidade1x
if %unidade1% equ y goto unidade1y
if %unidade1% equ w goto unidade1w
if %unidade1% equ z goto unidade1z
if %unidade1% geq 1 goto invuni2

:unidade1c
cls
echo.
md %USERPROFILE%\Desktop\Outlook\
md %USERPROFILE%\Desktop\Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %USERPROFILE%\Desktop\Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %USERPROFILE%\Desktop\Outlook\Outlook-Roaming
rd %USERPROFILE%\Desktop\Outlook\
cls
set uni=C
goto local1

:unidade1d
cls
echo.
md %dd%Outlook\
md %dd%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %dd%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %dd%Outlook\Outlook-Roaming
rd %dd%Outlook\
cls
set uni=D
goto local1

:unidade1e
cls
echo.
md %ee%Outlook\
md %ee%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ee%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ee%Outlook\Outlook-Roaming
rd %ee%Outlook\
cls
set uni=E
goto local1

:unidade1f
cls
echo.
md %ff%Outlook\
md %ff%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ff%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ff%Outlook\Outlook-Roaming
rd %ff%Outlook\
cls
set uni=F
goto local1

:unidade1g
cls
echo.
md %gg%Outlook\
md %gg%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %gg%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %gg%Outlook\Outlook-Roaming
rd %gg%Outlook\
cls
set uni=G
goto local1

:unidade1h
cls
echo.
md %hh%Outlook\
md %hh%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %hh%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %hh%Outlook\Outlook-Roaming
rd %hh%Outlook\
cls
set uni=H
goto local1

:unidade1i
cls
echo.
md %ii%Outlook\
md %ii%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ii%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ii%Outlook\Outlook-Roaming
rd %ii%Outlook\
cls
set uni=I
goto local1

:unidade1j
cls
echo.
md %jj%Outlook\
md %jj%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %jj%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %jj%Outlook\Outlook-Roaming
rd %jj%Outlook\
cls
set uni=J
goto local1

:unidade1k
cls
echo.
md %kk%Outlook\
md %kk%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %kk%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %kk%Outlook\Outlook-Roaming
rd %kk%Outlook\
cls
set uni=K
goto local1

:unidade1l
cls
echo.
md %ll%Outlook\
md %ll%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ll%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ll%Outlook\Outlook-Roaming
rd %ll%Outlook\
cls
set uni=L
goto local1

:unidade1m
cls
echo.
md %mm%Outlook\
md %mm%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %mm%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %mm%Outlook\Outlook-Roaming
rd %mm%Outlook\
cls
set uni=M
goto local1

:unidade1n
cls
echo.
md %nn%Outlook\
md %nn%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %nn%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %nn%Outlook\Outlook-Roaming
rd %nn%Outlook\
cls
set uni=N
goto local1

:unidade1o
cls
echo.
md %oo%Outlook\
md %oo%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %oo%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %oo%Outlook\Outlook-Roaming
rd %oo%Outlook\
cls
set uni=O
goto local1

:unidade1p
cls
echo.
md %pp%Outlook\
md %pp%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %pp%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %pp%Outlook\Outlook-Roaming
rd %pp%Outlook\
cls
set uni=P
goto local1

:unidade1q
cls
echo.
md %qq%Outlook\
md %qq%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %qq%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %qq%Outlook\Outlook-Roaming
rd %qq%Outlook\
cls
set uni=Q
goto local1

:unidade1r
cls
echo.
md %rr%Outlook\
md %rr%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %rr%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %rr%Outlook\Outlook-Roaming
rd %rr%Outlook\
cls
set uni=R
goto local1

:unidade1s
cls
echo.
md %ss%Outlook\
md %ss%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ss%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ss%Outlook\Outlook-Roaming
rd %ss%Outlook\
cls
set uni=S
goto local1

:unidade1t
cls
echo.
md %tt%Outlook\
md %tt%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %tt%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %tt%Outlook\Outlook-Roaming
rd %tt%Outlook\
cls
set uni=T
goto local1

:unidade1u
cls
echo.
md %uu%Outlook\
md %uu%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %uu%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %uu%Outlook\Outlook-Roaming
rd %uu%Outlook\
cls
set uni=U
goto local1

:unidade1v
cls
echo.
md %vv%Outlook\
md %vv%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %vv%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %vv%Outlook\Outlook-Roaming
rd %vv%Outlook\
cls
set uni=V
goto local1

:unidade1w
cls
echo.
md %ww%Outlook\
md %ww%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %ww%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %ww%Outlook\Outlook-Roaming
rd %ww%Outlook\
cls
set uni=W
goto local1

:unidade1x
cls
echo.
md %xx%Outlook\
md %xx%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %xx%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %xx%Outlook\Outlook-Roaming
rd %xx%Outlook\
cls
set uni=X
goto local1

:unidade1y
cls
echo.
md %yy%Outlook\
md %yy%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %yy%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %yy%Outlook\Outlook-Roaming
rd %yy%Outlook\
cls
set uni=Y
goto local1

:unidade1z
cls
echo.
md %zz%Outlook\
md %zz%Outlook\Outlook-Roaming
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\outlook\*.* %zz%Outlook\Outlook-Roaming
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %zz%Outlook\Outlook-Roaming
rd %zz%Outlook\
cls
set uni=Z
goto local1


##########################################################################################################
##########################################################################################################

:local1
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Backup da pasta ROAMING na %uni% em Outlook\Outlook-Roaming                    º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE BACKUP
pause > nul
goto menu1

##########################################################################################################
##########################################################################################################

:backup3
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Copiando arquivos PST da pasta DOCUMENTOS para Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
md %USERPROFILE%\Desktop\Outlook\
md %USERPROFILE%\Desktop\Outlook\PST
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\Documents\+++++++\*.* %USERPROFILE%\Desktop\Outlook\PST
echo OBS: O xcopy ainda falta verificar o nome curto no Prompt de Comando no Windows XP para ser colado aqui!!!
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %USERPROFILE%\Desktop\Outlook\PST
rd %USERPROFILE%\Desktop\Outlook\
cls
goto local2

:local2
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Backup da pasta PST na Area de Trabalho em Outlook\PST no Windows XP    º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE BACKUP
pause > nul
goto menu1

##########################################################################################################
##########################################################################################################

:backup4
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Copiando arquivos ASSINATURAS\DICIONARIO\MODELOS\PAPEL DE CARTA da pasta ROAMING para Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
md %USERPROFILE%\Desktop\Outlook\
md %USERPROFILE%\Desktop\Outlook\Assinaturas\Signatures
md %USERPROFILE%\Desktop\Outlook\Dicionario\UProof
md %USERPROFILE%\Desktop\Outlook\Modelos\Templates
md %USERPROFILE%\Desktop\Outlook\Papel_de_carta\Stationery
echo.
echo ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo º Pastas Criadas com sucesso!  º
echo ÌÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¹             
echo º Realizando Agora os Backups! º
echo ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\Signatures\*.* %USERPROFILE%\Desktop\Outlook\Assinaturas\Signatures
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\UProof\*.* %USERPROFILE%\Desktop\Outlook\Dicionario\UProof
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\Templates\*.* %USERPROFILE%\Desktop\Outlook\Modelos\Templates
%xcopy% %USERPROFILE%\AppData\Roaming\Microsoft\Stationery\*.* %USERPROFILE%\Desktop\Outlook\Papel_de_carta\Stationery
echo.
echo Precione qualquer tecla para continuar.
pause > nul
rd %USERPROFILE%\Desktop\Outlook\Assinaturas\Signatures
rd %USERPROFILE%\Desktop\Outlook\Dicionario\UProof
rd %USERPROFILE%\Desktop\Outlook\Modelos\Templates
rd %USERPROFILE%\Desktop\Outlook\Papel_de_carta\Stationery
rd %USERPROFILE%\Desktop\Outlook\Assinaturas\
rd %USERPROFILE%\Desktop\Outlook\Dicionario\
rd %USERPROFILE%\Desktop\Outlook\Modelos\
rd %USERPROFILE%\Desktop\Outlook\Papel_de_carta\
rd %USERPROFILE%\Desktop\Outlook\
cls
goto local3

:local3
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Backup das pastas ASSINATURAS, DICIONARIO, MODELOS e Papel de Carta na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE BACKUP
pause > nul
goto menu1


##########################################################################################################
##########################################################################################################
##########################################################################################################
##########################################################################################################


:restaurar1
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Restaurando arquivos Outlook na Area de Trabalho para pasta Outlook     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\Desktop\Outlook\Outlook-local\*.* %USERPROFILE%\AppData\Local\Microsoft\outlook
echo.
echo Precione qualquer tecla para continuar.
pause > nul
cls
goto local

:local
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Restauracao dos arquivos Outlook     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE RESTAURACAO
pause > nul
goto menu2

##########################################################################################################
##########################################################################################################

:restaurar2
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Restaurando arquivos Outlook na Area de Trabalho para pasta ROAMING     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\Desktop\Outlook\Outlook-Roaming\*.* %USERPROFILE%\AppData\Roaming\Microsoft\outlook
echo.
echo Precione qualquer tecla para continuar.
pause > nul
cls
goto local1

:local1
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Restauracao dos arquivos Outlook     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE RESTAURACAO
pause > nul
goto menu2

##########################################################################################################
##########################################################################################################

:restaurar3
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Restaurando arquivos PST na Area de Trabalho para pasta DOCUMENTOS     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
%xcopy% %USERPROFILE%\Desktop\Outlook\PST\*.* %USERPROFILE%\Documents\+++++++
echo OBS: O xcopy ainda falta verificar o nome curto no Prompt de Comando no Windows XP para ser colado aqui!!!
echo.
echo Precione qualquer tecla para continuar.
pause > nul
cls
goto local2

:local2
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Restauracao dos arquivos do Outlook em Documentos no Windows XP     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE RESTAURACAO
pause > nul
goto menu2

##########################################################################################################
##########################################################################################################

:restaurar4
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Restaurando arquivos ASSINATURAS\DICIONARIO\MODELOS\PAPEL DE CARTA da pasta ROAMING     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
%xcopy% %USERPROFILE%\Desktop\Outlook\Assinaturas\Signatures\*.* %USERPROFILE%\AppData\Roaming\Microsoft\Signatures
%xcopy% %USERPROFILE%\Desktop\Outlook\Dicionario\UProof\*.* %USERPROFILE%\AppData\Roaming\Microsoft\UProof
%xcopy% %USERPROFILE%\Desktop\Outlook\Modelos\Templates\*.* %USERPROFILE%\AppData\Roaming\Microsoft\Templates
%xcopy% %USERPROFILE%\Desktop\Outlook\Papel_de_carta\Stationery\*.* %USERPROFILE%\AppData\Roaming\Microsoft\Stationery
echo.
echo Precione qualquer tecla para continuar.
pause > nul
cls
goto local3

:local3
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizado Restauracao dos arquivos ASSINATURAS, DICIONARIO, MODELOS e Papel de Carta     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU DE RESTAURACAO
pause > nul
goto menu2


##########################################################################################################
##########################################################################################################
##########################################################################################################
##########################################################################################################

:perfil1
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office 2003 na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\2003\
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\11.0\Outlook\Profiles %USERPROFILE%\Desktop\Office\2003\RegistroProfileOutlook.reg /y /reg:64
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\11.0\Outlook\PST %USERPROFILE%\Desktop\Office\2003\RegistroPSTOutlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\2003\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto menu3

##########################################################################################################
##########################################################################################################

:perfil2
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office 2007 na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\2007\
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\12.0\Outlook\Profiles %USERPROFILE%\Desktop\Office\2007\RegistroProfileOutlook.reg /y /reg:64
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\12.0\Outlook\PST %USERPROFILE%\Desktop\Office\2007\RegistroPSTOutlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\2007\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU SALVAR PERFIL
pause > nul
cls
goto menu3

##########################################################################################################
##########################################################################################################

:perfil3
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office 2010 na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\2010\
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Outlook\Profiles %USERPROFILE%\Desktop\Office\2010\RegistroProfileOutlook.reg /y /reg:64
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Outlook\PST %USERPROFILE%\Desktop\Office\2010\RegistroPSTOutlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\2010\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU SALVAR PERFIL
pause > nul
cls
goto menu3

##########################################################################################################
##########################################################################################################

:perfil4
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office 2013 na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\2013\
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Outlook\Profiles %USERPROFILE%\Desktop\Office\2013\RegistroProfileOutlook.reg /y /reg:64
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Outlook\PST %USERPROFILE%\Desktop\Office\2013\RegistroPSTOutlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\2013\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU SALVAR PERFIL
pause > nul
cls
goto menu3

##########################################################################################################
##########################################################################################################

:perfil5
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office 2016 na Area de Trabalho     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\2016\
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Outlook\Profiles %USERPROFILE%\Desktop\Office\2016\RegistroProfileOutlook.reg /y /reg:64
REG EXPORT HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Outlook\PST %USERPROFILE%\Desktop\Office\2016\RegistroPSTOutlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\2016\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU SALVAR PERFIL
pause > nul
cls
goto menu3

##########################################################################################################
##########################################################################################################

:perfil6
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º     Realizando Backup de registro do Office (Todas as Versoes Mais Antigas)     º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
md %USERPROFILE%\Desktop\Office\
md %USERPROFILE%\Desktop\Office\OutraVersao\
REG EXPORT "HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\Windows Messaging Subsystem\Profiles" %USERPROFILE%\Desktop\Office\Registro-Perfil-Outlook.reg /y /reg:64
echo.
rd %USERPROFILE%\Desktop\Office\OutraVersao\
rd %USERPROFILE%\Desktop\Office\
echo Precione qualquer tecla para continuar.
pause > nul
cls
echo.
echo    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo    º OBS: Se a pasta for deletada, nao houve backup para essa versao do Office º
echo    ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
echo Precione qualquer tecla para voltar ao MENU SALVAR PERFIL
pause > nul
cls
goto menu3


##########################################################################################################
##########################################################################################################
##########################################################################################################
##########################################################################################################


:invalida
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra opcao do Menu º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto menu

:invalida1
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra opcao do Menu  º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto menu1

:invalida2
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra opcao do Menu  º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto menu2

:invalida3
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra opcao do Menu º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto menu3

##########################################################################################################
##########################################################################################################

:invuni1
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra Unidade º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto backup1

:invuni2
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra Unidade º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto backup2

:invuni3
echo.
echo   ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»
echo   º Opcao Invalida! Escolha outra Unidade º
echo   ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
echo.
pause
cls
goto backup3

##########################################################################################################
##########################################################################################################

:voltar1
cls
goto menu1

:voltar2
cls
goto menu2

:voltar3
cls
goto menu3

:sair
cls
exit
