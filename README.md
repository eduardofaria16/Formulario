<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8"/>
<title>Formulario</title> 
<link rel="stylesheet" type="text/css" href="estilo.css">

</head>
<body>
    <header>   
        <h1> Formulario </h1>
        <section>

        
            <form action="" method="post" >
            <label for="nome"> Nome: </label>
            <input type="text" name="nome" id="idnome"><br>
            <label for="telefone">Telefone: </label>
            <input type="int" name="telefone" id="idtelefone"><br>
            <label for="email">Email: </label>
            <input type="email" name="email" id="idemail"><br>
            

            <input type="submit" value="Enviar">

            <?php
            include('conexao.php');

           if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $nome = $_POST['nome'];
    $telefone = $_POST['telefone'];
    $email = $_POST['email'];

    $sql = "INSERT INTO dadosform (nome, telefone, email) VALUES ('$nome', '$telefone', '$email')";

    if ($conn->query($sql) === TRUE) {
        echo "Dados inseridos com sucesso!";
    } else {
        echo "Erro: " . "<br>" . $conn->error;
    }
    }

         $conn->close();
     ?>
        </form>
        </section>
    </header>






</body>
</html>
