# addition-8
org 100h
b db 22h
l db 19h
start:
     mov al,b
     add al,l
     mov bl,al
     mov ah, al
     and ah, 0F0h     
     shr ah, 4        
     add ah, 30h      
     cmp ah, 39h       
     jle first
     add ah, 7       
 first:
      mov dl, ah     
      mov ah, 02h    
      int 21h
      mov ah, bl
      and ah, 0Fh     
      add ah, 30h      
      cmp ah, 39h
      jle sec
      add ah, 7       
 sec:
       mov dl, ah      
       mov ah, 02h    
       int 21h
       mov ah, 4Ch
       int 21h
ret
