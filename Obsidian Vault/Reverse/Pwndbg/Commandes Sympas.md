Chose la plus basique (adresse trouvée via binja, ghidra..) : 

```bash
b *0x<adresse>
r <param>
info reg rdi # Print la valeur assignée au registre associé
```

Si breakpoint casse le programme (chall no software breakpoints) : 

```bash
hbreak *0x<adresse>
```


Changer la commande assembly  d'une adresse en NOP (Changer 0x90 à l'adresse souhaitée..) : 
```bash
set *(char *)0x<adresse> = 0x90  # Pour x86, 0x90 est l'opcode NOP
```

Nanomites : 
```bash
set follow-fork-mode parrent|child
```

