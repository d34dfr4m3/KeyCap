# KeyCap
Ferramenta de CTF. Encontrei o script em uma writeup e peguei pra mim, fiz umas alterações e tal, mas no final das contas não deu certo e n tinha nada a ver, mas vou postar o script porquê é massa
## Steps
- Você primeiro precisava converter o arquivo pcap em plaintext, (na real faz mt tempo e eu n lembro)
- Ai tinha o comando de baixo, que é possível assim como não é possivel que seja no plaintext ou direto no pcap. ELe vai extrair o "payload" dos "pacotes". 
```
 tshark -r feel-it -Y "((usb.transfer_type == 0x01) &&  (frame.len == 72))" -e "usb.capdata" -Tfields  
```
- Depois era só executar o script para mapear os valores.
- Provavelmente isso ta errado, mas tem uns papers ai em baixo que foi de onde eu tirei o script e conhecimentos. 

####### Papers:
- https://medium.com/@ali.bawazeeer/kaizen-ctf-2018-reverse-engineer-usb-keystrok-from-pcap-file-2412351679f4
- https://superuser.com/questions/873896/wireshark-usb-traces-explanations
- https://www.beyondlogic.org/usbnutshell/usb4.shtml#Interrupt
- http://www.usb.org/developers/hidpage/Hut1_12v2.pdf
