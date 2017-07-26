## git自动提交代码的脚本


#! /bin/bash

echo "git add ."
git add .

read -p "输入提交日志:" log

echo "git commit -m $log"
git commit -m $log

read -p "是否提交到远程?[y/n]" input

case $input in
    [yY][eE][sS]|[yY])
                read -p "请输入分支名称:" branch
                echo "git push origin $branch"
                git push origin $branch
                ;;

    [nN][oO]|[nN])
                echo "暂时不提交远程仓库"
                ;;

esac
