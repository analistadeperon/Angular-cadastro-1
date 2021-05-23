<hello name="{{ name }}"></hello>
<p>
  Start working today :)
</p>
<html lang="en">
  <img class="img-responsive" src="https://w1.pngwing.com/pngs/68/88/png-transparent-world-logo-partnership-business-partner-company-management-small-business-business-administration-reseller-thumbnail.png">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <meta name="description" content="">
        <meta name="author" content="">        
        <title>Teste CNPJ</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
    </head>

    <body>

        <!-- Modal -->
        <div class="modal fade" id="captchaModal" tabindex="-1" role="dialog" aria-hidden="true">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header">
                        <button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
                        <h4 class="modal-title" id="myModalLabel">Captcha</h4>
                    </div>
                    <div class="modal-body">
                        <img src="<?php echo $params['captchaBase64'] ?>" /><br /><br />
                        <input type="text" class="form-control" id="captcha" placeholder="Informe os caracteres da imagem acima" />
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-default" data-dismiss="modal">Fechar</button>
                        <button type="button" class="btn btn-primary" id="consultarCNPJ">Consultar</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Container -->
        <div class="container">
            <div class="page-header">
                <h1>Cadastro de empresa</h1>
            </div>

            <form role="form">
                <div class="form-group">
                    <label>Informe o CNPJ:</label>
                    <div class="input-group">
                        <input type="text" class="form-control" id="cnpj" />
                        <span class="input-group-btn">
                            <button class="btn btn-default" data-toggle="modal" data-target="#captchaModal" type="button">Consultar</button>
                        </span>
                    </div>
                </div>

                <div class="form-group">
                    <label>Razão social:</label>
                    <input type="text" class="form-control" id="razao_social">
                </div>

                <div class="form-group">
                    <label>Nome fantasia:</label>
                    <input type="text" class="form-control" id="nome_fantasia">
                </div>

                <div class="form-group">
                    <label>Fundação:</label>
                    <input type="text" class="form-control" id="fundacao">
                </div>
                <div class="form-group">
                    <label>Telefone:</label>
                    <input type="text" class="form-control" id="telefone">
                </div>

                <div class="form-group">
                    <label>Endereço:</label>
                    <input type="text" class="form-control" id="endereco">
                </div>              
            </form>

        </div><!-- /.container -->

        <script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script>

        <script>
            $(function() {
                $("#consultarCNPJ").click(function() {
                    var btn = $(this);
                    var old = btn.html();

                    var param = {
                        cnpj: $("#cnpj").val(),
                        captcha: $("#captcha").val(),
                        cookie: '<?php echo $params['cookie'] ?>'
                    };

                    btn.html('Aguarde! Consultando..');

                    $.post("consulta.php", param, function(json) {

                        if (json.code === 0) {

                            $('#razao_social').val(json.razao_social);
                            $('#nome_fantasia').val(json.nome_fantasia);
                            $('#fundacao').val(json.data_abertura);

                            var endereco = json.logradouro + ' ';
                            endereco += json.numero + ' ';
                            endereco += json.complemento + ' ';
                            endereco += '- ' + json.bairro + ' ';
                            endereco += '- Cep:' + json.cep + ' ';
                            endereco += '- ' + json.cidade + '/' + json.uf;

                            $('#endereco').val(endereco);
                        } else
                            alert(json.message);

                        btn.html(old);
                        $('#captchaModal').modal('hide');

                    }, "json");

                });
            });
        </script>
    </body>
</html>
 <button id="Cadastrar" name="Cadastrar" class="btn btn-success" type="Submit">Cadastrar</button>
<input type="text" class="form-control" id="cartao-credito">
 
<label for="cartao-credito" class="radio-item__label">Cartão de debito</label>
<button id="Credito" name="Credito" class="btn btn-success" type="Submit">Pagar</button>

<label for="debito" class="radio-item__label">Cartão de credito</label>

<button id="debito" name="debito" class="btn btn-success" 
type="Submit">Pagar</button>
<form>
  <div class="form-group">
    <label for="exampleFormControlFile1">Exemplo de input de arquivo</label>
    <input type="file" class="form-control-file" id="exampleFormControlFile1">
  </div>
   <button type="submit" class="btn btn-primary">Atualizar</button>
</form>
<form>
  <img class="img-responsive" src="https://espep.pb.gov.br/imagens/icones/ficha-pre-inscricao/@@images/08a578c7-a91c-42eb-b0c0-5ed4e168a474.jpeg">
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputEmail4">Email</label>
      <input type="email" class="form-control" id="inputEmail4" placeholder="Email">
    </div>
    <div class="form-group col-md-6">
      <label for="inputPassword4">Senha</label>
      <input type="password" class="form-control" id="inputPassword4" placeholder="Senha">
    </div>
  </div>
  <div class="form-group">
    <label for="inputAddress">Endereço emprego</label>
    <input type="text" class="form-control" id="inputAddress" placeholder="Rua dos Bobos, nº 0">
  </div>
  <div class="form-group">
    <label for="inputAddress2">Endereço Residencial</label>
    <input type="text" class="form-control" id="inputAddress2" placeholder="Apartamento, hotel, casa, etc.">
  </div>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputCity">Cidade</label>
      <input type="text" class="form-control" id="inputCity">
    </div>
    <div class="form-group col-md-4">
      <label for="inputEstado">Estado</label>
      <select id="inputEstado" class="form-control">
        <option selected>SP...</option>
        <option selected>RJ...</option>
        <option selected>GO...</option>
        <option selected>MT...</option>
        <option selected>TO...</option>
        <option selected>PR...</option>
        <option selected>RS...</option>
        <option>...</option>
      </select>
    </div>
    <div class="form-group col-md-2">
      <label for="inputCEP">CEP</label>
      <input type="text" class="form-control" id="inputCEP">
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" id="gridCheck">
      <label class="form-check-label" for="gridCheck">
        Clique em mim
      </label>
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Entrar</button>
 </form>
 <label for="inputPassword5">Senha</label><button>aqui<button>
<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
<small id="passwordHelpBlock" class="form-text text-muted">
  Sua senha deve ter entre 8 e 20 caracteres, os quais devem ser letras e números, sem espaços, caracteres especiais ou emojis.
</small>
<div class="ui container">
  <div></div>
  <h2 class="ui center aligned header">Cadastro de Cliente</h2>
  <form class="ui form">
    <div class="field">
      <label>Nome</label>
      <input type="text" name="nome" placeholder="Nome Completo" maxlength="50">
    </div>
    <div class="field">
      <label>Cpf</label>
      <input type="text" name="cpf" placeholder="xxx.xxx.xxx-xx" maxlength="14">
    </div>
    <div class="field">
      <label>Cnpj</label>
      <input type="text" name="cnpj" placeholder="xx.xxx.xxx/xxxx-xx" maxlength="18">
    </div>
    </form>
</div>
<label for="inputPassword5">Senha</label>
  <div class="ui blue submit button">Salvar</div> <button>aqui<button>
<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
<small id="passwordHelpBlock" class="form-text text-muted">
  Sua senha deve ter entre 8 e 20 caracteres, os quais devem ser letras e números, sem espaços, caracteres especiais ou emojis.
    
