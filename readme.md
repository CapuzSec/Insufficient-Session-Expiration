#### Pessoal, mais cuidado ao desenvolver sua aplicação, encontrei uma falha em uma bastante conhecida e usada por empresas como Santander, Ibm, Volvo, Coca-cola, entre outras.


#### A falha simplesmente ocorre por falta de quebra de sessão. 
#### Digamos que um hacker consegue acesso a sua conta, poderiamos simplesmente usar a função "Mudar Senha ou Recuperar Senha" para barrar o mesmo. 
#### Quando solicitado, deveria invalidar todas as sessões antigas ou de outros aparelhos, porem, o hacker ainda continua logado e  realizando alterações no perfil da pessoa normalmente. 


#### Lembrando que a conta usada nessa pesquisa foi criada por mim, sendo assim, não foi violado usuários terceiros!
#  


Vamos pedir uma redefinição de senha ou usar a função esqueci a senha, em ambas existe essa vulnerabilidade.




No caso abaixo vamos mudar a senha simplesmente como se o usuário tivesse recebido um e-mail em que a plataforma lhe avisa que ouve um acesso indesejado em sua conta.




![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Formulario_Altera_Senha.PNG)


#






Mensagem de senha alterada com sucesso.






![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Senha_Alterada.PNG)


#






Senha alterada, agora podemos ver a requisição no Burp Suite onde o final da senha antiga consiste em "E999" e a nova em "E000" 


![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Senha_Alterada.PNG)






#






Resposta 200 OK (Senha alterada com sucesso)


![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Senha_Alterada_200_OK.PNG)






# 






Apos a alteração deveria ser quebrada todas as demais sessões. 


Mas o hacker ainda continua logado conseguindo executar qualquer função na conta desse usuário. Mesmo com a mudança da senha, pode se alterar dados da conta ou algo pior.


Agora alteramos novamente, sendo a antiga com final "E000" e a nova "E111"




![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Repeater_Request_Senha.PNG)






#






Retornando novamente resposta 200 OK (Senha alterada com sucesso)
 
![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Repeater_Request_Senha_200_OK.PNG)






#






Depois simplesmente realizamos uma requisição para confirmar o ato, e observamos que retorna uma resposta 200 ok sem nenhum problema!


Fazendo a função de alteração de senha se tornar inutil para parte de segurança, servindo apenas para realizar um login qualquer na plataforma.

![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Repeater_Request_User.PNG)
![Alt Text](https://github.com/giovane999/Insufficient-Session-Expiration/blob/master/Burp_Repeater_200_Ok.PNG)
