---
title: "Gewusst wie: Hinzuf&#252;gen von Steuerelementen zu Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Hinzufügen"
  - "Windows Forms-Steuerelemente, Hinzufügen zum Formular"
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Hinzuf&#252;gen von Steuerelementen zu Windows&#160;Forms
Die meisten Formulare werden entworfen, indem der Formularoberfläche Steuerelemente hinzugefügt werden, um so eine Benutzeroberfläche zu entwickeln.  Ein *Steuerelement* ist eine Komponente in einem Formular. Es wird verwendet, um Informationen anzuzeigen oder Benutzereingaben zu akzeptieren.  Weitere Informationen zu Steuerelementen finden Sie unter [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So zeichnen Sie ein Steuerelement in einem Formular  
  
1.  Öffnen Sie das Formular.  Weitere Informationen hierzu finden Sie unter [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/de-de/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Klicken Sie in der **Toolbox** auf das Steuerelement, das zum Formular hinzugefügt werden soll.  
  
3.  Klicken Sie im Formular auf die Stelle, an der die obere linke Ecke des Steuerelements positioniert werden soll, und ziehen Sie den Mauszeiger an die Stelle, an der die untere rechte Ecke des Steuerelements positioniert werden soll.  
  
     Das Steuerelement wird mit der angegebenen Größe und Position in das Formular eingefügt.  
  
    > [!NOTE]
    >  Jedes Steuerelement verfügt über eine vordefinierte Standardgröße.  Um dem Formular ein Steuerelement in Standardgröße hinzuzufügen, ziehen Sie es aus der **Toolbox** in das Formular.  
  
### So ziehen Sie ein Steuerelement in ein Formular  
  
1.  Öffnen Sie das Formular.  Weitere Informationen hierzu finden Sie unter [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/de-de/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Klicken Sie in der **Toolbox** auf das gewünschte Steuerelement, und ziehen Sie es in das Formular.  
  
     Das Steuerelement wird in seiner Standardgröße an der angegebenen Position in das Formular eingefügt.  
  
    > [!NOTE]
    >  Sie können auf ein Steuerelement in der **Toolbox** doppelklicken, um es in seiner Standardgröße in der linken oberen Ecke des Formulars einzufügen.  
  
     Steuerelemente können dem Formular auch dynamisch zur Laufzeit hinzugefügt werden.  Im folgenden Codebeispiel wird dem Formular ein <xref:System.Windows.Forms.TextBox>\-Steuerelement hinzugefügt, wenn auf ein <xref:System.Windows.Forms.Button>\-Steuerelement geklickt wird.  
  
    > [!NOTE]
    >  Für die folgende Prozedur ist ein Formular erforderlich, auf dem bereits das **Button**\-Steuerelement `Button1` platziert ist.  
  
### So fügen Sie einem Formular ein Steuerelement programmgesteuert hinzu  
  
1.  Geben Sie in der Methode, durch die das `Click`\-Ereignis der Schaltfläche innerhalb der Formularklasse behandelt wird, mit dem folgenden Beispiel vergleichbaren Code ein, um einen Verweis auf die Steuerelementvariable hinzuzufügen. Legen Sie die `Location`\-Eigenschaft für das Steuerelement fest, und fügen Sie das Steuerelement hinzu:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  Sie können auch Code hinzufügen, um weitere Steuerelementeigenschaften zu initialisieren.  
  
    > [!IMPORTANT]
    >  Unter Umständen setzen Sie den lokalen Computer über das Netzwerk einem Sicherheitsrisiko aus, wenn Sie auf ein schädliches `UserControl` verweisen.  Allerdings ist dies nur dann ein Problem, wenn ein böswilliger Benutzer ein schädliches benutzerdefiniertes Steuerelement erstellt, das Sie versehentlich zu dem Projekt hinzufügen.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)   
 [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)