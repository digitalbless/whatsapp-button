 ## Tema Pursuit

- Passo 1: Acesse seu tema e entre em "Loja Virtual", clique nos "..." no seu tema e vá em "Editar Código".
- Passo 2: Pesquise na barra de pesquisa por "theme.liquid" , a linha do codigo que necessita de alteração está entre "243 - 249", a alteração deve ser feita como mostra o exemplo: "https://api.whatsapp.com/send?phone=5583998989898", após o "=" insira o numero desejado, sem espaço e sem nenhum tipo de caractere, após a alteração clique em salvar no canto superior direito.

<img src="https://user-images.githubusercontent.com/105664296/216088391-65c5463e-2a8f-408d-a826-f8a3cf9c09bf.png"  />

## Tema Warehouse

- Passo 1: Acesse seu tema e entre em "Loja Virtual", clique nos "..." no seu tema e vá em "Editar Código".
- Passo 2: Pesquise na barra de pesquisa por "theme.liquid" , a linha do codigo que necessita de alteração está entre "159 - 163", a alteração deve ser feita como mostra o exemplo: "https://api.whatsapp.com/send?phone=5583998989898", após o "=" insira o numero desejado, sem espaço e sem nenhum tipo de caractere, após a alteração clique em salvar no canto superior direito.

<img src="https://user-images.githubusercontent.com/105664296/216104257-52602da0-03ce-44d9-9489-4d33052090ba.png"  />

<br/>

# Como inserir o botão em qualquer tema

- Passo 1: Acesse seu tema e entre em "Loja Virtual", clique nos "..." no seu tema e vá em "Editar Código".
- Passo 2: Acesse primeiramente o theme.css e insira esse techo de código 

    		
    		.lp-whatsapp-icon-container {
    		   position: fixed !important;
    		   right: 50px;
    		   bottom: 0;
    		  -webkit-transform: translateY(-50%);
    		  -ms-transform: translateY(-50%);
    		   transform: translateY(-50%);
    		   z-index: 9999999999999999;
    		}
      
            @media screen and (max-width:749px) {
               .lp-whatsapp-icon-container {
               display: none;
             }
            }
    
    		  .lp-whatsapp-icon-bar a {
    		  border: 1px solid #A8A8A8;
    		  display: block;
    		  text-align: center;
    		  transition: all 0.3s ease;
    		}
    
    		.lp-whatsapp-icon-container:hover {
    		 scale: 1.025;
    		 transition: all 0.3s ease;
    		}
      
- Passo 3: Acesse o theme.liquid e insira esse código de preferencia no final do arquivo, porém dentro do body e do html como as imagens acima exemplificam.

     		 <div class="lp-whatsapp-icon-container">
    			  <a href="https://api.whatsapp.com/send?phone=558398507016" target="blank">
    				<img src="https://cdn.shopify.com/s/files/1/0607/6091/6161/files/botao_whatsapp-01.png?v=1675263058" width="60">
    			  </a>
    		  </div>

- Passo 4:  Por ultimo, escolha sua imagem e adicione ao seus arquivos no shopify, vá em "configurações" canto inferior esquerdo, depois em "arquivos", e insira sua imagem, depois do upload feito, clique no gerador de link do lado, "O icone com o símbolo do clipe de papel", volte no arquivo theme.liquid, e vá onde você colou o trecho do código do Passo 3, altere a linha descrita na imagem abaixo;

<img  src="https://user-images.githubusercontent.com/105664296/216109535-b5e7410e-3f4c-4052-b3b6-d6e37afd359e.png"/>


# Disponibilizando o botão pelo personalizar

- Passo 1 :  Ainda no editar código, vá em "config", depois em "settings_schema.json" e insira esse código no final do arquivo depois da ultima chave, insira uma " , " e cole esse código abaixo;

      		 {
    				 "name": "WhatsApp",
    				 "settings": [
    				 {
    				 "type": "text",
    				 "id": "whatsapp_icon_number",
    				 "label": "Whatsapp Number",
    				 "default": "971000000000"
    				 },
    				 {
    				 "type": "text",
    				 "id": "whatsapp_icon_image",
    				 "label": "Whatsapp Image Link",
    				 "default": "LINK"
    				 }
    				 ]
    				 }

###### Obs: a tag default:"LINK" é onde você deve colocar o link da imagem que você importou anteriormente.

- Passo 2: Volte no arquivo theme.liquid e onde você inseriu o código anterior faça essas alterações;

         <div class="lp-whatsapp-icon-container">
          <a href="https://api.whatsapp.com/send?phone={{settings.whatsapp_icon_number}}">
           <img src="{{settings.whatsapp_icon_image}}" width="60">
          </a>
         </div>
