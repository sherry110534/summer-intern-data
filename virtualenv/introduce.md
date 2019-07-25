# 虛擬環境(virtual environment)

注：

* Python2.7.9之後Python2系列版本和Python3.4之後Python3系列版本都已加入`pip`模組，不需要額外安裝
* 若不確定可用` pip --version`檢查
* 上網查python虛擬環境會出現`virtualenv`和`venv`兩種指令，前者是獨立的模組，後者附屬在Python3中。
  * 網路上說Python3.3之後的版本內建venv了，但我在linux(python 3.5)上測試並沒有，還是要安裝QAQ

### 優點

- 你的專案會擁有一個專屬的獨立 Python 環境。
- 不需要 root 權限，就可以安裝新套件。
- 方便控管不同版本的套件，不用擔心升級套件會影響到其他專案。
- 如果需要多人協作或在不同機器上跑同一個專案時，使用虛擬環境也可以確保環境一致性。

### 建立虛擬環境

從terminal下指令建立虛擬環境，下指令後會出現虛擬環境的資料夾

#### windows

```
python -m venv venv_name
```

#### Linux/OS X

注：

* linux/OS X上內建Python2，比較新的版本會同時內建Python2/3，因此下Python指令指的是Python2，windows則不一定，看使用者當初如何安裝

* 有需要可使用`sudo apt-get install python3.6`安裝
* 若不確定版本，可用` python --version`指令檢查

```
python3 -m venv venv_name
```

建立出來的虛擬環境資料夾可參考`test_venv`，大小約27.8M

### 切換虛擬環境

* 虛擬環境資料夾中的Scripts中有`activate`腳本，執行即可切換(linux/os x在bin資料夾中)
* 在安裝新套件或執行程式前都要記得切換

#### windows

下面這行是假設目前在虛擬環境的資料夾中的相對路徑，看你目前在哪個資料夾，把腳本找出來直接執行即可

```
Scripts\activate
```

#### Linux/OS X

這裡也是相對路徑喔

```
source bin/activate
```

或者

```
. bin/activate
```

成功後會長這樣，就可以開始做事了

```
(venv_name)terminal前墜資料使用者名稱目前路徑那些有的沒的>
```

### 結束虛擬環境

```
deactivate
```

這樣就跳出來啦

### 紀錄安裝的套件名稱和版本

列出並寫檔

```
pip freeze > requirements.txt
```

單純列出來看

```
 pip list
```

利用requirement.txt一次安裝所有套件

```
 pip install -r requirements.txt
```

### 參考資料

* [Django Girl](<https://djangogirlstaipei.gitbooks.io/django-girls-taipei-tutorial/django/installation.html>)