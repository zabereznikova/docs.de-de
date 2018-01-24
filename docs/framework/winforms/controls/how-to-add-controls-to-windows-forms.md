---
title: "Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab92f7a56173ec71642d0cc09f3f81e9859533b4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-controls-to-windows-forms"></a>Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms
Die meisten Formulare werden durch Hinzufügen von Steuerelementen auf die Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren. Ein *Steuerelement* ist eine Komponente in einem Formular zum Anzeigen von Informationen oder annehmen von Benutzereingaben verwendet. Weitere Informationen zu Steuerelementen finden Sie unter [Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-draw-a-control-on-a-form"></a>Zum Zeichnen eines Steuerelements in einem Formular  
  
1.  Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  In der **Toolbox**, klicken Sie auf das Steuerelement dem Formular hinzufügen möchten.  
  
3.  Klicken Sie auf der linken oberen Ecke des Steuerelements befinden soll, und ziehen Sie in der unteren rechten Ecke des Steuerelements befinden soll, auf dem Formular.  
  
     Das Steuerelement wird in das Formular mit der angegebenen Position und Größe hinzugefügt.  
  
    > [!NOTE]
    >  Jedes Steuerelement verfügt über eine Standardgröße definiert. Sie können ein Steuerelement zum Formular in Standardgröße des Steuerelements hinzufügen, indem Sie ziehen es aus der **Toolbox** in das Formular.  
  
### <a name="to-drag-a-control-to-a-form"></a>Ziehen Sie ein Steuerelement zu einem Formular  
  
1.  Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  In der **Toolbox**, klicken Sie auf das Steuerelement, Sie möchten, und ziehen Sie es in Ihr Formular.  
  
     Das Steuerelement wird dem Formular an der angegebenen Position in der Standardgröße hinzugefügt.  
  
    > [!NOTE]
    >  Sie können ein Steuerelement in Doppelklicken Sie auf die **Toolbox** der oberen linken Ecke des Formulars in der Standardgröße hinzuzufügen.  
  
     Sie können auch Steuerelemente dynamisch zu einem Formular zur Laufzeit hinzufügen. Im folgenden Codebeispiel eine <xref:System.Windows.Forms.TextBox> Steuerelement wird dem Formular hinzugefügt werden bei einem <xref:System.Windows.Forms.Button> Steuerelement geklickt wird.  
  
    > [!NOTE]
    >  Das folgende Verfahren erfordert das Vorhandensein eines Formulars mit einem **Schaltfläche** Steuerelement `Button1`, bereits platziert ist.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Programmgesteuertes Hinzufügen des Steuerelements zu einem Formular  
  
1.  In der Methode, die der Schaltfläche behandelt `Click` Ereignisses innerhalb der Formularklasse Code einfügen, die etwa wie folgt einen Verweis auf die Steuerelementvariable hinzufügen festlegen, welches Steuerelement `Location`, und fügen Sie das Steuerelement.  
  
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
    >  Sie können auch Code zum Initialisieren der anderen Eigenschaften des Steuerelements hinzufügen.  
  
    > [!IMPORTANT]
    >  Sie können den lokalen Computer über das Netzwerk ein Sicherheitsrisiko verfügbar zu machen, durch Verweisen auf ein böswilliger `UserControl`. Dies ist nur relevant, wenn ein böswilliger Benutzer, erstellen ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
