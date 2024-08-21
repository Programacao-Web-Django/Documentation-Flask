# Exemplos de Aplicações Flask

Aqui estão alguns exemplos de aplicações Flask simples para ajudar você a começar a praticar e entender como o Flask funciona. Estes exemplos cobrem diferentes aspectos da criação de aplicações web usando Flask.

## Exemplo 1: Aplicação Hello World

Este é o exemplo mais básico de uma aplicação Flask, que simplesmente retorna "Hello, World!" quando a raiz da aplicação é acessada.

        
        from flask import Flask

        app = Flask(__name__)

        @app.route('/')
        def hello_world():
            return 'Hello, World!'

        if __name__ == '__main__':
            app.run(debug=True)


## Exemplo 2: Roteamento com Parâmetros

Este exemplo mostra como criar uma rota que aceita parâmetros de URL e os utiliza dentro da função de rota


        from flask import Flask

        app = Flask(__name__)

        @app.route('/greet/<name>')
        def greet(name):
            return f'Hello, {name}!'

        if __name__ == '__main__':
            app.run(debug=True)
