---
title: "Internationale Schriftarten in Windows&#160;Forms und Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Schriftart-Fallback in Windows Forms"
  - "Schriftarten, Überlegungen zur Globalisierung"
  - "Schriftarten, International"
  - "Globalisierung [Windows Forms], Zeichensätze"
  - "Internationale Anwendungen [Windows Forms], Zeichenanzeige"
  - "Lokalisierung [Windows Forms], Schriftarten"
  - "Windows Forms-Steuerelemente, Bezeichnungen"
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Internationale Schriftarten in Windows&#160;Forms und Steuerelementen
Für internationale Anwendungen sollte möglichst die automatische Schriftartauswahl verwendet werden.  Automatische Schriftartauswahl bedeutet, dass das System bestimmt, zu welcher Schrift ein Zeichen gehört.  
  
## Verwenden der automatischen Schriftartauswahl  
 Legen Sie die <xref:System.Drawing.Font>\-Eigenschaft für das Formular oder ein beliebiges anderes Element nicht fest, wenn Sie dieses Feature nutzen möchten.  Die Anwendung greift in diesem Fall automatisch auf die Standardschrift des Systems zurück, die sich nach der Sprache richtet, in die das Betriebsystem lokalisiert wurde.  Wenn die Anwendung ausgeführt wird, stellt das System automatisch die richtige Schrift für die im Betriebssystem ausgewählte Kultur bereit.  
  
 Es gibt jedoch eine Ausnahme zu der Regel, dass die Schrift nicht festgelegt wird. Sie betrifft die Änderung des Schriftschnitts.  In einer Anwendung kommt sie dann zum Tragen, wenn der Benutzer auf eine Schaltfläche klickt, um Text in einem Textfeld in Fettschrift darzustellen.  Dazu würden Sie eine Funktion schreiben, die auf der Grundlage der Formularschrift den Schriftschnitt des Textfelds in fett ändert.  Diese Funktion muss unbedingt an zwei Stellen aufgerufen werden: im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler der Schaltfläche und im <xref:System.Windows.Forms.Control.FontChanged>\-Ereignishandler.  Wenn die Funktion nur im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler aufgerufen und die Schriftfamilie des gesamten Formulars durch anderen Code geändert wird, ändert sich das Textfeld nicht mit dem restlichen Formular.  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 Beim Lokalisieren der Anwendung wird die Fettschrift jedoch in bestimmten Sprachen möglicherweise nur mangelhaft dargestellt.  Wenn dies Probleme aufwirft, sollten die Lokalisierungsspezialisten die Möglichkeit haben, die Schrift von fett auf normalen Text umzuschalten.  Da Lokalisierungsspezialisten in der Regel keine Entwickler sind und nur Zugriff auf die Ressourcendateien, jedoch nicht auf den Quellcode haben, muss diese Option in den Ressourcendateien festgelegt werden.  Zu diesem Zweck würden Sie die <xref:System.Drawing.Font.Bold%2A>\-Eigenschaft auf `true` festlegen.  Dadurch wird die Schrifteinstellung in die Ressourcendateien geschrieben, wo sie von den Lokalisierungsspezialisten bearbeitet werden kann.  Fügen Sie anschließend nach der `InitializeComponent` \-Methode Code ein, der die Schriftart auf die Formularschrift zurücksetzt, dabei jedoch den in der Ressourcendatei festgelegten Schriftschnitt verwendet.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## Siehe auch  
 [Globalisieren von Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)   
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)