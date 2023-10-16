 ;Programa hello world
 ;Introdução ao Assembly
 ;Autor: Maria Julia, FEAP
 
SYS_EXIT      equ 1 ;informa uma interrupção de entrada/saída
SYS_READ      equ 3 
SYS_WRITE     equ 4
STDIN         equ 0
STDOUT        equ 1
  
section .data ;seção de dados
    msg db 'Hello, word'
    len equ $ -msg ;para exibir a msg

section .text ;iniciar seção de texto/mensagem e alocação de memória
    global _start ;coleção de dados declarados
    
_start:
    mov edx, len ;comprimento da mensagem
    mov ecx, msg ;mensagem para escrever
    mov ebx, STDOUT ;descritor dp arquivo (saída)
    mov eax, SYS_WRITE ;descritor do arquivo (entrada)
    int 0x80 ;chamada kernel
    mov eax, 1
    int 0x80 ; chamada kernel   
    
    
