# Criando e Registrando Blueprints em Flask

Blueprints são uma maneira poderosa de estruturar e organizar grandes aplicações Flask em componentes menores e reutilizáveis. Abaixo está um guia passo a passo sobre como criar e registrar blueprints em uma aplicação Flask.

## Criando Blueprints


Primeiro, crie um novo arquivo Python para definir o blueprint. Por exemplo, crie um arquivo chamado `main.py` na pasta `blueprints`:

### `blueprints/main.py`

        from flask import Blueprint

        # Criação do Blueprint
        bp = Blueprint('main', __name__)

        # Definição de Rotas
        @bp.route('/')
        def home():
            return 'Página Inicial'

        @bp.route('/about')
        def about():
            return 'Sobre a Página'

## Registrando um Blueprint

Depois de criar um blueprint, você deve registrá-lo na aplicação principal. Isso é feito usando o método register_blueprint da instância da aplicação Flask. Veja como registrar o blueprint criado anteriormente:

        from flask import Flask

        app = Flask(__name__)

        # Registrando o blueprint
        app.register_blueprint(modulo)
