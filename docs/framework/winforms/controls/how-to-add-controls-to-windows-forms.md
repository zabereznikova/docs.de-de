---
title: Hinzufügen von Steuerelementen
description: Erfahren Sie, wie Sie ein Steuerelement in einem Windows Form zeichnen. Ein-Steuerelement ist eine Komponente in einem Formular, das Sie verwenden können, um Informationen anzuzeigen oder Benutzereingaben zu akzeptieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325877"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms

Die meisten Formulare werden durch das Hinzufügen von Steuerelementen zur Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren. Ein- *Steuer* Element ist eine Komponente auf einem Formular, mit dem Informationen angezeigt oder Benutzereingaben akzeptiert werden. Weitere Informationen zu-Steuerelementen finden Sie unter Windows Forms-Steuer [Elemente](index.md).

## <a name="to-draw-a-control-on-a-form"></a>So zeichnen Sie ein Steuerelement in einem Formular

1. Öffnen Sie das Formular. Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. Klicken Sie in der **Toolbox**auf das Steuerelement, das Sie dem Formular hinzufügen möchten.

3. Klicken Sie im Formular auf die Stelle, an der sich die obere linke Ecke des Steuer Elements befinden soll, und ziehen Sie an die Stelle, an der die untere rechte Ecke des Steuer Elements platziert werden soll.

    Das-Steuerelement wird dem Formular mit der angegebenen Position und Größe hinzugefügt.

    > [!NOTE]
    > Für jedes Steuerelement ist eine Standardgröße definiert. Sie können dem Formular ein Steuerelement in der Standardgröße des Steuer Elements hinzufügen, indem Sie es aus der **Toolbox** in das Formular ziehen.

## <a name="to-drag-a-control-to-a-form"></a>So ziehen Sie ein Steuerelement in ein Formular

1. Öffnen Sie das Formular. Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. Klicken Sie in der **Toolbox**auf das gewünschte Steuerelement, und ziehen Sie es in das Formular.

    Das-Steuerelement wird dem Formular an der angegebenen Position in seiner Standardgröße hinzugefügt.

    > [!NOTE]
    > Sie können auf ein Steuerelement in der **Toolbox** doppelklicken, um es der oberen linken Ecke des Formulars in seiner Standardgröße hinzuzufügen.

    Sie können einem Formular auch zur Laufzeit dynamisch Steuerelemente hinzufügen. Im folgenden Codebeispiel <xref:System.Windows.Forms.TextBox> wird dem Formular ein-Steuerelement hinzugefügt, wenn auf ein- <xref:System.Windows.Forms.Button> Steuerelement geklickt wird.

    > [!NOTE]
    > Für das folgende Verfahren ist es erforderlich, dass ein Formular mit einem **Schalt** Flächen-Steuerelement vorhanden ist, das `Button1` bereits darauf platziert ist.

## <a name="to-add-a-control-to-a-form-programmatically"></a>So fügen Sie einem Formular ein Steuerelement Programm gesteuert hinzu

1. Fügen Sie in der-Methode, die das-Ereignis der Schaltfläche `Click` in der-Klasse des Formulars behandelt, Code ähnlich dem folgenden hinzu, um einen Verweis auf die Steuerelement Variable hinzuzufügen, die des Steuer Elements festzulegen `Location` und das Steuerelement hinzuzufügen.

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
    > Sie können auch Code hinzufügen, um andere Eigenschaften des Steuer Elements zu initialisieren.

    > [!IMPORTANT]
    > Sie können den lokalen Computer mit einem Sicherheitsrisiko über das Netzwerk verfügbar machen, indem Sie auf eine böswillige verweisen `UserControl` . Dies wäre nur ein Problem, wenn eine böswillige Person ein schädliches benutzerdefiniertes Steuerelement erstellt, gefolgt von dem, das Sie versehentlich dem Projekt hinzufügen.

## <a name="see-also"></a>Siehe auch

- [Windows Forms Steuerelemente](index.md)
- [Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
