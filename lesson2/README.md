NEW LINE

# исключить все файлы в директории terraform не зависимо в какой папке она находится
**/.terraform/*

# исключить все файлы с расширением .tfstate и .tfstate.любое
*.tfstate
*.tfstate.*

# Исключить файл crash.log
crash.log

# исключить все файлы с расширением .tfvars
*.tfvars

# исключить файл override.tf и override.tf.json 
override.tf 
override.tf.json

# исключить все файлы с окончанием _override.tf и _override.tf.json
*_override.tf
*_override.tf.json

# исключить файлы с расширением Ignore CLI configuration files
.terraformrc
terraform.rc
