<?php
$conn = mysqli_connect("localhost", "root", "", "gra_rpg"); 
# **Działa** i łączy sie z bazą danych
?>

<style>
    th, td {
        border: 1px solid black;
    }
</style>


<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table>
        <tr>
            <th>id_drzewko</th>
            <th>id_rasy</th>
            <th>nazwa</th>
            <th>opis</th>
        </tr>
<?php
$query = "SELECT * FROM drzewko";
$result = mysqli_query($conn, $query);

if ($result) {
    while ($linijka = mysqli_fetch_assoc($result)) {
        echo "<tr>";
        echo "<td>".$linijka['id_drzewko']."</td>";
        echo "<td>".$linijka['id_rasy']."</td>";
        echo "<td>".$linijka['nazwa']."</td>";
        echo "<td>".$linijka['opis']."</td>";
        echo "</tr>"; # nie mam pojęcia czemu i jak to działa ale działa
    }
}
?>

    </table>
</body>
</html>

<?php
    mysqli_close($conn);
?>
