# criar-um-arquivo-.BAT
 como criar um arquivo

*/Arquivo .bat (batch) executavel a cada 15 segundos ou mais./*
@ECHO OFF
title CleanerproX By Marcos
chcp 1252 > Nul
set Intervalo=15
mode 30,13
color 0c
:menu
cls
echo [1] Limpar memoria
echo [2] Sair
echo [3] Ram Programada
echo.
set/p menu=">"

if %menu% equ 1 goto :voltar
if %menu% equ 2 exit
if %menu% equ 3 (goto :ram) else (cls& echo Opção inválida& pause& goto :menu)

:ram
cls
%windir%\system32\rundll32.exe advapi32.dll,ProcessIdleTasks
echo Executando Limpeza da RAM a cada %Intervalo% segundos
echo.
timeout /t %Intervalo%
goto :ram
exit

:voltar
set a= °
cls
echo.
echo BAT PARA LIMPAR A MEMORIA RAM!
echo.
set n=0
echo.
:limpa
echo.
ECHO -----------PASSANDO.RODO-----------
ECHO.
echo.
echo.
timeout /t 3
del /s /f /q c:\windows\temp\*.*
rd /s /q c:\windows\temp
md c:\windows\temp
del /s /f /q "%temp%\*.*"
rd /s /q "%temp%"
md "%temp%"
del /s /f /q c:\windows\temp\*.*
del /s /f /q  c:\windows\prefetch\*.*
del /s /f /q  "c:\windows\Downloaded Program Files\*.*"
del /s /f /q  c:\windows\Installer\*.*
%windir%\system32\rundll32.exe advapi32.dll,ProcessIdleTasks
cls
