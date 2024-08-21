# Validação de Formulários com Flask-WTF

A validação de formulários é essencial para garantir que os dados recebidos do usuário sejam válidos e estejam no formato correto. Flask-WTF, que utiliza WTForms, oferece uma série de validadores para facilitar esse processo. 

## Validadores Comuns

### DataRequired

O validador `DataRequired` assegura que o campo não seja deixado em branco. É útil para campos que são obrigatórios.

    from flask_wtf import FlaskForm
    from wtforms import StringField
    from wtforms.validators import DataRequired

    class MyForm(FlaskForm):
        name = StringField('Name', validators=[DataRequired()])
