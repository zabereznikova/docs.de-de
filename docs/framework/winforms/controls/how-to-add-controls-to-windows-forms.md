---
title: 'Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 31820775d4f7fb981599e806aa5e27655039e6ac
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720773"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms
Die meisten Formulare werden durch Hinzufügen der Steuerelemente auf die Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren. Ein *Steuerelement* ist eine Komponente in einem Formular zum Anzeigen von Informationen oder Benutzereingaben akzeptieren. Weitere Informationen zu Steuerelementen, finden Sie unter [Windows Forms-Steuerelemente](index.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-control-on-a-form"></a>Zum Zeichnen eines Steuerelements in einem Formular  
  
1.  Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2.  In der **Toolbox**, klicken Sie auf das Steuerelement zum Formular hinzufügen möchten.  
  
3.  Klicken Sie auf dem Formular klicken Sie auf der linken oberen Ecke des Steuerelements abgelegt werden sollen, und ziehen Sie in der unteren rechten Ecke des Steuerelements abgelegt werden sollen.  
  
     Das Steuerelement wird zum Formular mit der angegebenen Position und Größe hinzugefügt.  
  
    > [!NOTE]
    >  Jedes Steuerelement verfügt über eine Standardgröße definiert. Sie können ein Steuerelement zum Formular in Standardgröße des Steuerelements hinzufügen, durch Ziehen aus dem **Toolbox** auf das Formular.  
  
### <a name="to-drag-a-control-to-a-form"></a>Ziehen Sie ein Steuerelement zu einem Formular  
  
1.  Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2.  In der **Toolbox**, klicken Sie auf das Steuerelement, Sie möchten, und ziehen Sie es in Ihrem Formular.  
  
     Das Steuerelement wird dem Formular an der angegebenen Position in der Standardgröße hinzugefügt.  
  
    > [!NOTE]
    >  Sie können ein Steuerelement in Doppelklicken Sie auf die **Toolbox** der oberen linken Ecke des Formulars in der Standardgröße hinzufügen.  
  
     Sie können auch Steuerelemente dynamisch zu einem Formular zur Laufzeit hinzufügen. Das folgende Codebeispiel zeigt eine <xref:System.Windows.Forms.TextBox> Steuerelement wird dem Formular hinzugefügt werden bei einer <xref:System.Windows.Forms.Button> -Steuerelement geklickt wird.  
  
    > [!NOTE]
    >  Das folgende Verfahren erfordert das Vorhandensein eines Formulars mit einem **Schaltfläche** Steuerelement `Button1`, bereits platziert ist.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>So ein Formular ein Steuerelement programmgesteuert hinzu  
  
1.  In der Methode, die der Schaltfläche verarbeitet `Click` Ereignissatz innerhalb der Formularklasse Code einfügen, die etwa wie folgt einen Verweis auf die Steuerelementvariable Hinzufügen des Steuerelements `Location`, und fügen Sie das Steuerelement.  
  
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
    >  Sie können den lokalen Computer ein Sicherheitsrisiko dar, über das Netzwerk verfügbar zu machen, durch Verweisen auf ein böswilliger `UserControl`. Dies wäre nur ein Problem, wenn ein böswilliger Benutzer erstellt ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.  
  
## <a name="see-also"></a>Siehe auch
- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Vorgehensweise: Größe von Steuerelementen in Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
