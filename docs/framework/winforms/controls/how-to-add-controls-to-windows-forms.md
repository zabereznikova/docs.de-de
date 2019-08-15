---
title: 'Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 5c57d86b2f08733dc4a729bf6091eab23c6035f2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039710"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms
Die meisten Formulare werden durch das Hinzufügen von Steuerelementen zur Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren. Ein- *Steuer* Element ist eine Komponente auf einem Formular, mit dem Informationen angezeigt oder Benutzereingaben akzeptiert werden. Weitere Informationen zu-Steuerelementen finden Sie unter Windows Forms-Steuer [Elemente](index.md).

## <a name="to-draw-a-control-on-a-form"></a>So zeichnen Sie ein Steuerelement in einem Formular

1. Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Zeigen Sie Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))an.

2. Klicken Sie in der **Toolbox**auf das Steuerelement, das Sie dem Formular hinzufügen möchten.

3. Klicken Sie im Formular auf die Stelle, an der sich die obere linke Ecke des Steuer Elements befinden soll, und ziehen Sie an die Stelle, an der die untere rechte Ecke des Steuer Elements platziert werden soll.

     Das-Steuerelement wird dem Formular mit der angegebenen Position und Größe hinzugefügt.

    > [!NOTE]
    >  Für jedes Steuerelement ist eine Standardgröße definiert. Sie können dem Formular ein Steuerelement in der Standardgröße des Steuer Elements hinzufügen, indem Sie es aus der **Toolbox** in das Formular ziehen.

## <a name="to-drag-a-control-to-a-form"></a>So ziehen Sie ein Steuerelement in ein Formular

1. Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Zeigen Sie Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))an.

2. Klicken Sie in der **Toolbox**auf das gewünschte Steuerelement, und ziehen Sie es in das Formular.

     Das-Steuerelement wird dem Formular an der angegebenen Position in seiner Standardgröße hinzugefügt.

    > [!NOTE]
    >  Sie können auf ein Steuerelement in der **Toolbox** doppelklicken, um es der oberen linken Ecke des Formulars in seiner Standardgröße hinzuzufügen.

     Sie können einem Formular auch zur Laufzeit dynamisch Steuerelemente hinzufügen. Im folgenden Codebeispiel wird dem Formular <xref:System.Windows.Forms.TextBox> ein-Steuerelement hinzugefügt, wenn auf <xref:System.Windows.Forms.Button> ein-Steuerelement geklickt wird.

    > [!NOTE]
    >  Für das folgende Verfahren ist es erforderlich, dass ein Formular mit einem Schalt `Button1`Flächen-Steuerelement vorhanden ist, das bereits darauf platziert ist.

## <a name="to-add-a-control-to-a-form-programmatically"></a>So fügen Sie einem Formular ein Steuerelement Programm gesteuert hinzu

1. Fügen Sie in der-Methode, die `Click` das-Ereignis der Schaltfläche in der-Klasse des Formulars behandelt, Code ähnlich dem folgenden hinzu, um einen Verweis auf die Steuer `Location`Element Variable hinzuzufügen, die des Steuer Elements festzulegen und das Steuerelement hinzuzufügen.

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
    >  Sie können auch Code hinzufügen, um andere Eigenschaften des Steuer Elements zu initialisieren.

    > [!IMPORTANT]
    >  Sie können den lokalen Computer mit einem Sicherheitsrisiko über das Netzwerk verfügbar machen, indem Sie auf `UserControl`eine böswillige verweisen. Dies wäre nur ein Problem, wenn eine böswillige Person ein schädliches benutzerdefiniertes Steuerelement erstellt, gefolgt von dem, das Sie versehentlich dem Projekt hinzufügen.

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Vorgehensweise: Ändern der Größe von Steuerelementen auf Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Vorgehensweise: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
