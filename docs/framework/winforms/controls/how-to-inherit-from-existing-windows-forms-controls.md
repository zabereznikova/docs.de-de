---
title: Erben von vorhandenen Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849379"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen

Wenn Sie die Funktionalität eines vorhandenen Steuerelements erweitern möchten, können Sie ein Steuerelement erstellen, dass durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist. Beim Erben von einem vorhandenen Steuerelement erben Sie die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements. Wenn Sie z. B. ein Steuerelement <xref:System.Windows.Forms.Button>erstellen, das von geerbt wurde, <xref:System.Windows.Forms.Button> würde das neue Steuerelement genau wie ein Standardsteuerelement aussehen und sich verhalten. Sie können die Funktionalität Ihres neuen Steuerelements durch Implementieren von benutzerdefinierten Methoden und Eigenschaften erweitern oder ändern. In einigen Steuerelementen können Sie auch die visuelle Darstellung des <xref:System.Windows.Forms.Control.OnPaint%2A> geerbten Steuerelements ändern, indem Sie seine Methode überschreiben.

## <a name="to-create-an-inherited-control"></a>So erstellen Sie ein geerbtes Steuerelement

1. Erstellen Sie in Visual Studio ein neues **Windows Forms Application-Projekt.**

1. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

    Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

1. Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.

    Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.

1. Wenn Sie verwenden:

    - Visual Basic, oben im **Projektmappen-Explorer**, klicken Sie auf **Alle Dateien anzeigen**. Erweitern Sie „CustomControl1.vb“ und öffnen Sie „CustomControl1.Designer.vb“ im Code-Editor.
    - Öffnen Sie CustomControl1.cs im Code-Editor.

1. Suchen Sie die Klassendeklaration, die von erbt. <xref:System.Windows.Forms.Control>

1. Ändern Sie die Basisklasse in das Steuerelement, von dem Sie erben möchten.

     Wenn Sie z. B. von <xref:System.Windows.Forms.Button>erben möchten, ändern Sie die Klassendeklaration wie folgt:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Wenn Sie Visual Basic verwenden, speichern und schließen Sie „CustomControl1.Designer.vb“. Öffnen Sie „CustomControl1.vb“ im Code-Editor.

1. Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.

1. Wenn Sie die grafische Darstellung des Steuerelements <xref:System.Windows.Forms.Control.OnPaint%2A> ändern möchten, überschreiben Sie die Methode.

    > [!NOTE]
    > Durch <xref:System.Windows.Forms.Control.OnPaint%2A> das Überschreiben können Sie die Darstellung aller Steuerelemente nicht ändern. Die Steuerelemente, die alle ihre Malerei von <xref:System.Windows.Forms.TextBox>Windows (zum Beispiel) gemacht haben, rufen niemals ihre <xref:System.Windows.Forms.Control.OnPaint%2A> Methode auf und werden daher niemals den benutzerdefinierten Code verwenden. In der Hilfedokumentation finden Sie das jeweilige Steuerelement, <xref:System.Windows.Forms.Control.OnPaint%2A> das Sie ändern möchten, um festzustellen, ob die Methode verfügbar ist. Eine Liste aller Windows Form-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md). Wenn ein Steuerelement <xref:System.Windows.Forms.Control.OnPaint%2A> nicht als Membermethode aufgeführt ist, können Sie seine Darstellung nicht ändern, indem Sie diese Methode überschreiben. Weitere Informationen über benutzerdefinierte Darstellung finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. Speichern und testen Sie das Steuerelement.

## <a name="see-also"></a>Weitere Informationen

- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)
- [Vorgehensweise: Erben von der Control-Klasse](how-to-inherit-from-the-control-class.md)
- [Gewusst wie: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
