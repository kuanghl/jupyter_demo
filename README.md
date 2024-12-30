
#### jupyter books

- [参考:](https://daobook.github.io/jupyter-book-zh/content/index.html)

```sh
# linux
# 更新python
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.12
sudo apt install python3.12-full
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 1  
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
sudo update-alternatives --config python3
sudo apt-get purge python3.8
sudo apt-get autoremove
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --force-reinstall
sudo rm -rf deadsnakes-ubuntu-ppa-focal.list 
python3 -m pip install --upgrade pip
# pip install --upgrade sphinx==6
# pip install sphinx-book-theme # >=1.1.0
# pip install quantecon-book-theme
pip install --upgrade myst-parser sphinxcontrib-bibtex sphinx-design
pip install --upgrade jupyter-book quantecon-book-theme
pip install git+https://github.com/QuantEcon/quantecon-book-theme.git
# _config.yml文件中添加以下code
sphinx:
    config:
        html_theme: quantecon_book_theme
# 新建demo
pip install -U jupyter-book
jupyter-book create jupyter_demo
cd jupyter_demo
jupyter-book build -W -n --keep-going --all .
# 其他指令
jb -h
jb create jupyter_demo/
jb build jupyter_demo/
jb clean jupyter_demo/

# windows
conda install git
git clone https://github.com/eoas-ubc/quantecon-mini-example.git
cd quantecon-mini-example
git checkout windows
conda env create -f environment_win.yml
conda activate wintest
cd mini_book
runjb docs
start docs\_build\html\index.html

# vscode拓展
@tag:notebookKernelJupyterNotebook Jupyter

# 上传到github
pip install ghp-import
cd jupyter_demo/
ghp-import -n -p -f _build/html
# 访问:https://<user>.github.io/<jupyter_demo>/
```