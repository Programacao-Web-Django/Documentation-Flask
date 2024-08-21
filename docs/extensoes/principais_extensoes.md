# Principais Extensões do Flask

Flask possui um rico ecossistema de extensões que podem adicionar funcionalidades essenciais à sua aplicação. Abaixo estão algumas das principais extensões usadas na comunidade Flask, cada uma com sua descrição e exemplos de uso.

## Flask-SQLAlchemy

**Descrição**: Integra o SQLAlchemy com Flask, fornecendo uma camada ORM para interagir com bancos de dados relacionais de forma mais fácil e intuitiva.

- **Instalação**: `pip install flask-sqlalchemy`
- **Documentação**: [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/latest/)

**Exemplo de Uso**:


    from flask import Flask
    from flask_sqlalchemy import SQLAlchemy 

    app = Flask(__name__)
    app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///meubanco.db'
    db = SQLAlchemy(app)

    class User(db.Model):
        id = db.Column(db.Integer, primary_key=True)
        username = db.Column(db.String(80), unique=True, nullable=False)

    @app.before_first_request
    def create_tables():
        db.create_all()

    @app.route('/add_user/<username>')
    def add_user(username):
        new_user = User(username=username)
        db.session.add(new_user)
        db.session.commit()
        return f'Usuário {username} adicionado com sucesso!' 

