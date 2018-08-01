# PyQt5

"""
instagram:
@kubilaypayci

"""

import sys
from PyQt5 import QtWidgets,QtGui

hayat = ["\n\n\n\n\n   Mustafa Kemal Atatürk 1881 yılında Selânik'te\n  Kocakasım Mahallesi, Islâhhâne Caddesi'ndeki\n   üç katlı pembe evde doğdu. Babası Ali Rıza E-\nfendi, annesi Zübeyde Hanım'dır. Baba tarafından \n  dedesi  Hafız Ahmet Efendi XIV-XV. yüzyıllarda\n Konya ve Aydın'dan Makedonya'ya yerleştirilmiş\nKocacık Yörüklerindendir. Annesi Zübeyde Hanım ise \n     Selânik yakınlarındaki Langaza kasabasına\n    yerleşmiş eski bir Türk ailesinin kızıdır. Milis\nsubaylığı, evkaf katipliği ve kereste ticareti yapan\n   Ali Rıza Efendi, 1871 yılında Zübeyde Hanım'la\nevlendi. Atatürk'ün beş kardeşinden dördü küçük\n    yaşlarda öldü, sadece Makbule (Atadan) 1956\n	           yılına değin yaşadı.","Ikinci","Ucuncu"]

class pencere(QtWidgets.QWidget):
	
	def __init__(self):
		
		super().__init__()
		
		self.init_ui()
	
	def init_ui(self):
		self.baslik = QtWidgets.QLabel("\n\nATATÜRK'ÜN HAYATI")
		self.index = 0
		self.yazi = QtWidgets.QLabel()
		self.yazi.setText(hayat[self.index])
		self.buton1 = QtWidgets.QPushButton("    Geri    ")
		self.buton2 = QtWidgets.QPushButton("    Ileri    ")
				
		
		hbox = QtWidgets.QHBoxLayout()
		
		hbox.addStretch()
		hbox.addWidget(self.buton1)
		hbox.addWidget(self.buton2)	
		hbox.addStretch()
		
		yazih = QtWidgets.QHBoxLayout()
		
		yazih.addStretch()
		yazih.addWidget(self.yazi)
		yazih.addStretch()
		
		baslikh = QtWidgets.QHBoxLayout()
		baslikh.addStretch()
		baslikh.addWidget(self.baslik)
		baslikh.addStretch()
		
		yaziv = QtWidgets.QVBoxLayout()
		
		yaziv.addLayout(baslikh)
		yaziv.addStretch()
		yaziv.addLayout(yazih)
		yaziv.addStretch()
				
		
		vbox = QtWidgets.QVBoxLayout()
		vbox.addLayout(yaziv)
		vbox.addStretch()
		vbox.addLayout(hbox)
	
		
		self.setLayout(vbox)
		
		self.buton1.clicked.connect(self.click)
		self.buton2.clicked.connect(self.click)
		self.show()
	def click(self):
		
		sender = self.sender()
		
		if sender.text() == "    Ileri    ":
			self.index += 1
			if self.index > len(hayat) - 1:
				self.index = 0
				self.yazi.setText(hayat[self.index])
			else:
				self.yazi.setText(hayat[self.index])
		elif sender.text() == "    Geri    ":
			
			if self.index == 0:
				self.index = 0
				self.yazi.setText(hayat[self.index])
			else:
				self.index -= 1
				self.yazi.setText(hayat[self.index])
			
		
app = QtWidgets.QApplication(sys.argv)

pencere1 = pencere()

sys.exit(app.exec_())
		
		
		
		
		
		
