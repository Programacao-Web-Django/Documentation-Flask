# Controle de Acesso

O controle de acesso é um aspecto crítico da segurança de uma aplicação web, garantindo que usuários autenticados tenham permissão para acessar recursos e executar ações específicas. Em Flask, isso pode ser implementado usando roles e permissões.

## Implementando Controle de Acesso

### Usando Roles

Um método comum para implementar controle de acesso é através de roles (ou papéis). Cada usuário pode ter um ou mais roles que determinam o que ele pode ou não fazer na aplicação.

Aqui está um exemplo básico de como implementar controle de acesso com base em roles usando Flask-Login e lógica personalizada:


    from flask import Flask, redirect, url_for
    from flask_login import LoginManager, UserMixin, login_user, login_required, logout_user, current_user
    from functools import wraps

    app = Flask(__name__)
    app.secret_key = 'segredo'
    login_manager = LoginManager(app)

    # Classe de Usuário com Roles
    class User(UserMixin):
        def __init__(self, id, role):
            self.id = id
            self.role = role

    @login_manager.user_loader
    def load_user(user_id):
        # Simulação de carregamento de usuário
        return User(user_id, 'admin')

    # Decorador para Checar Roles
    def role_required(role):
        def decorator(f):
            @wraps(f)
            def wrapper(*args, **kwargs):
                if current_user.role != role:
                    return redirect(url_for('unauthorized'))
                return f(*args, **kwargs)
            return wrapper
        return decorator

    @app.route('/admin')
    @login_required
    @role_required('admin')
    def admin_panel():
        return 'Painel de Administração'

    @app.route('/unauthorized')
    def unauthorized():
        return 'Acesso Negado'

    if __name__ == '__main__':
        app.run()
