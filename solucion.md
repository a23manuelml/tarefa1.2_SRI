## Tarefa 1.2 - Instalación de zonas mestras primarias en Windows Server

1. Instala o servidor DNS no equipo lukeskywalker. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando  nslookup -norecurse www.starwars.com localhost
**SOLUCIÓN:**

- Cambiamos o nombre do equipo:
        
    ![imaxe1.1](imaxes/solapt1.1.png)
    
- Poñemos IP estática:
    
    ![imaxe1.2](imaxes/solapt1.2.png)

- Nas suxerencias de raíz, engadimos en "copiar desde servidor": 8.8.8.8 e 10.0.4.1
    
    ![imaxe1.3](imaxes/solapt1.3.png)

- Comprobación (segue sen funcionar):
    
    ![imaxe1.4](imaxes/solapt1.4.png)

2.Configura o servidor DNS para que empregue como reenviador 8.8.8.8. pegando no documento de entrega a captura de pantalla da configuración do reenviador e a saída deste comando: nslookup -recurse www.starwars.com localhost
**SOLUCIÓN:**
- Engadimos reenviadores de Google:
    
    ![imaxe1.5](imaxes/solapt1.5.png)

- Saída do comando:
    
    ![imaxe1.6](imaxes/solapt1.6.png)

2. Instala unha zona primaria de resolución directa chamada "academia.jedi" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):
    - Tipo A: lukeskywalker con IP 192.168.20.101
    - Tipo A: benskywalker con IP 192.168.20.102
    - Tipo A: obiwankenobi con IP 192.168.56.152 e 192.168.56.153
    - Tipo A: hansolo con IP 192.168.56.105
    - Tipo A: leia con IP 192.168.56.106
    - Tipo A: anakinsolo con IP 192.168.56.106
    - Tipo CNAME mestrejedi a obiwankenobi
    - TIPO MX con prioridade 10 sobre o equipo hansolo
    - TIPO TXT "thon" con "un Jedi debe sentir a tensión entre os dous lados da Forza"
    - TIPO NS con benskywalker
Pega no documento de entrega a captura dos rexistros creados

**SOLUCION:**

- Poñemos o servidor DNS como el mesmo:
    
    ![imaxe2.1](imaxes/solapt2.1.png)

- NS para a zona directa e indirecta

    ![imaxe2.2](imaxes/solapt2.2.png)

- SOA da zona directa e da inversa:
    
    ![imaxe2.3](imaxes/solapt2.3.png)

- Rexistro de zona directa:

    ![imaxe2.4](imaxes/solapt2.4.png)

3. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo lukeskywalker, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o a captura dos rexistros da zona.

**SOLUCIÓN:**

- Rezistro de zona inversa:

    ![imaxe3.1](imaxes/solapt3.1.png)

4. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:

**SOLUCIÓN:**

- nslookup lukeskywalker.academia.jedi localhost
        
    ![imaxe4.1](imaxes/solapt4.1.png)

- nslookup hansolo.academia.jedi localhost

    ![imaxe4.2](imaxes/solapt4.2.png)

- nslookup leia.academia.jedi localhost

    ![imaxe4.3](imaxes/solapt4.3.png)

- nslookup anakinsolo.academia.jedi localhost

    ![imaxe4.4](imaxes/solapt4.4.png)

- nslookup academia.jedi localhost

    ![imaxe4.5](imaxes/solapt4.5.png)

- nslookup -q=mx academia.jedi localhost

    ![imaxe4.6](imaxes/solapt4.6.png)

- nslookup -q=ns academia.jedi localhost

    ![imaxe4.7](imaxes/solapt4.7.png)

- nslookup -q=soa academia.jedi localhost

    ![imaxe4.8](imaxes/solapt4.8.png)

- nslookup -q=txt thon.academia.jedi localhost

    ![imaxe4.9](imaxes/solapt4.9.png)

- nslookup 192.168.56.101 localhost

    ![imaxe4.10](imaxes/solapt4.10.png)
