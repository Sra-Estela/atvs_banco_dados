# WEB + Banco de Dados

````Python
from flask import Flask, jsonify
import pymysql

app = Flask(__name__)

# Configuração do banco de dados
db_config = {
    'host': 'localhost',
    'user': 'root',
    'password': 'usbw',
    'database': 'db_escola',
}

# Rota para realizar um SELECT usando código SQL
@app.route('/usuarios')
def get_usuarios():
    connection = pymysql.connect(**db_config)
   
    try:
        with connection.cursor() as cursor:
            # Executa o comando SQL
            sql = "SELECT * FROM TB_JOGADORES"
            cursor.execute(sql)
            # Obtém todos os resultados
            resultados = cursor.fetchall()
           
            # Converte os resultados em uma lista de dicionários
            usuarios = [{"jog_id": row[0], "jog_nome": row[1]} for row in resultados]
           
        return jsonify(usuarios)
   
    finally:
        connection.close()

if __name__ == "__main__":
    app.run(debug=True)
```
