# Visão Geral sobre Blueprints

No Flask, **Blueprints** são uma maneira de estruturar grandes aplicações em componentes menores e reutilizáveis. Blueprints permitem que você defina rotas, manipule erros e configure funcionalidades em módulos separados, que podem ser registrados em uma aplicação principal.

## Benefícios dos Blueprints

1. **Organização**: Facilita a organização do código em módulos distintos.
2. **Reutilização**: Permite criar módulos reutilizáveis que podem ser compartilhados entre diferentes projetos.
3. **Escalabilidade**: Torna a aplicação mais escalável ao permitir uma divisão clara das responsabilidades.

## Estrutura Básica de um Blueprint

Aqui está um exemplo básico de como criar e registrar um blueprint:

    from flask import Flask, Blueprint

    # Criação de um Blueprint
    bp = Blueprint('main', __name__)

    @bp.route('/')
    def home():
        return 'Home Page'

    # Criação da Aplicação Flask
    app = Flask(__name__)
    app.register_blueprint(bp)

    if __name__ == '__main__':
        app.run()
