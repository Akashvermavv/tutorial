如果您不是使用 Chromebook 的話，您可以 [跳過這個章節](http://tutorial.djangogirls.org/en/installation/#install-python)。 如果是的話，您的安裝過程將會有些許的不同。 您可以忽略其餘的安裝說明。

### Cloud IDE (PaizaCloud Cloud IDE, AWS Cloud9)

Cloud 9 這工具會提供一個程式碼編輯器(code editor)，並讓你存取一台位於網路上的電腦，使你可以透過它安裝、撰寫、以及執行軟體。 在這個教程指南中，Cloud 9 將能當作您的*本機電腦*來執行。 您仍將在終端機介面中執行指令，跟同學使用在 OS X、Ubuntu、或是 Windows 一樣，但是您的終端機是連接到一個由 Cloud 9 為您設定在其他地方的主機。 這是為cloud IDEs (PaizaCloud Cloud IDE, AWS Cloud9)設計的指南 您可以選擇其中一個cloud IDE，然後跟從它的指示操作。

#### PaizaCloud Cloud IDE

1. 到[PaizaCloud Cloud IDE](https://paiza.cloud/)
2. 建立帳戶
3. 點擊*新伺服器*及選擇Django應用程式
4. 點擊「終端機」按鈕（在視窗的左側）

現在你應該可以看到一個有左方有sidebar和按鈕的介面。點選“Terminal“按鈕，開啟這樣的命令提示視窗：

{% filename %}終端機{% endfilename %}

    $
    

The terminal on the PaizaCloud Cloud IDE is prepared for your instructions. You can resize or maximize that window to make it a bit bigger.

#### AWS Cloud9

目前，Cloud 9 要求您使用 AWS 帳號註冊並輸入信用卡資料。

1. 從 [Chrome 線上應用程式商店](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)安裝 Colud 9
2. 到[c9.io](https://c9.io)點擊及瀏覽*開始使用 AWS Cloud9*
3. 註冊一個 AWS 帳號（需要信用卡資料，但您可以免費使用）
4. 在 AWS 儀表板上，搜尋 *Cloud 9* 並按下。
5. 在 Cloud 9 儀表板上，按下*建立環境*
6. 將它命名為 *django-girls*
7. While configuring settings, select *Create a new instance for environment (EC2)* for "Environment Type" and the *t2.micro* "Instance type" (it should say "Free-tier eligible."). The default cost-saving setting is fine and you can keep the other defaults.
8. 點擊 *下一步*
9. 點擊 *建立環境*

Now you should see an interface with a sidebar, a big main window with some text, and a small window at the bottom that looks something like this:

{% filename %}bash{% endfilename %}

    yourusername:~/workspace $
    

This bottom area is your terminal. You can use the terminal to send instructions to the remote Cloud 9 computer. You can resize that window to make it a bit bigger.

### 虛擬環境 [Virtual Environment]

A virtual environment (also called a virtualenv) is like a private box we can stuff useful computer code into for a project we're working on. We use them to keep the various bits of code we want for our various projects separate so things don't get mixed up between projects.

運行:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3 -m venv myvenv
    source myvenv/bin/activate
    pip install django~={{ book.django_version }}
    

(請注意，我們在最後一行確實使用了一個符號：`~=` 喔)。

### GitHub

建立一個[GitHub](https://github.com)帳號

### PythonAnywhere

The Django Girls tutorial includes a section on what is called Deployment, which is the process of taking the code that powers your new web application and moving it to a publicly accessible computer (called a server) so other people can see your work.

This part is a little odd when doing the tutorial on a Chromebook since we're already using a computer that is on the Internet (as opposed to, say, a laptop). However, it's still useful, as we can think of our Cloud 9 workspace as a place for our "in progress" work and Python Anywhere as a place to show off our stuff as it becomes more complete.

Thus, sign up for a new Python Anywhere account at [www.pythonanywhere.com](https://www.pythonanywhere.com).