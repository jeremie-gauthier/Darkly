Existence d'un cookie 'I_am_admin' = '68934a3e9455fa72420237eb05902327'

Apres analyse du hash sur https://crackstation.net/:
	- Nous constatons que l'algorithme de hachage utilisee est 'md5'
	- Nous constatons que la chaine de caractere en resultant est 'false'

Nous creons donc un nouveau hash (md5) ayant pour valeur 'true'
sur le site https://www.md5hashgenerator.com/

Puis nous recuperons le hash resultant et remplacons la valeur du cookie 'I_am_admin' par celui-ci.


En rechargeant la page avec ce cookie modifie, une alert() js apparait, nous donnant le flag de resolution.

flag:
df2eb4ba34ed059a1e3e89ff4dfc13445f104a1a52295214def1c4fb1693a5c3