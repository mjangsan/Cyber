Vulnerability: SQL Injection

File: 
    /dvwa/vulnerabilities/sqli/source/low.php
    
Vulnerable line:
    $query = "SELECT ... WHERE id='$id'"

Why:
    $id comes directly from $_GET['id'] with no sanitisation

Proof:
    input 1' OR '1'='1 returns all users

Fix (Medium level):
    mysqli_real_escape_string() escapes quotes
