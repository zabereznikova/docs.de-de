---
title: 'Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fcf95e08296f5a8ec5a386ac614482c034e72c8b
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373235"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen

Wenn Sie die Funktionalität eines vorhandenen Steuerelements erweitern möchten, können Sie ein Steuerelement erstellen, dass durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist. Beim Erben von einem vorhandenen Steuerelement erben Sie die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements. Wenn Sie z. b. ein Steuerelement erstellen, das <xref:System.Windows.Forms.Button>von geerbt wurde, würde das neue Steuerelement Aussehen und genauso <xref:System.Windows.Forms.Button> Vorgehen wie ein Standard Steuerelement. Sie können die Funktionalität Ihres neuen Steuerelements durch Implementieren von benutzerdefinierten Methoden und Eigenschaften erweitern oder ändern. In einigen Steuerelementen können Sie auch die visuelle Darstellung des geerbten Steuer Elements ändern, indem <xref:System.Windows.Forms.Control.OnPaint%2A> Sie die zugehörige-Methode überschreiben.

## <a name="to-create-an-inherited-control"></a>So erstellen Sie ein geerbtes Steuerelement

1. Erstellen Sie in Visual Studio ein neues **Windows Forms-Anwendungs** Projekt.

1. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

    Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

1. Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.

    Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.

1. Wenn Sie Folgendes verwenden:

    - Klicken Sie Visual Basic oben in **Projektmappen-Explorer**auf **alle Dateien anzeigen**. Erweitern Sie „CustomControl1.vb“ und öffnen Sie „CustomControl1.Designer.vb“ im Code-Editor.
    - C#Öffnen Sie CustomControl1.cs im Code-Editor.

1. Suchen Sie nach der Klassen Deklaration, die <xref:System.Windows.Forms.Control>von erbt.

1. Ändern Sie die Basisklasse in das Steuerelement, von dem Sie erben möchten.

     Wenn Sie z. b. von <xref:System.Windows.Forms.Button>erben möchten, ändern Sie die Klassen Deklaration wie folgt:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Wenn Sie Visual Basic verwenden, speichern und schließen Sie „CustomControl1.Designer.vb“. Öffnen Sie „CustomControl1.vb“ im Code-Editor.

1. Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.

1. Wenn Sie die grafische Darstellung des Steuer Elements ändern möchten, überschreiben Sie <xref:System.Windows.Forms.Control.OnPaint%2A> die-Methode.

    > [!NOTE]
    > <xref:System.Windows.Forms.Control.OnPaint%2A> Wenn Sie überschreiben, können Sie die Darstellung aller Steuerelemente nicht ändern. Diese Steuerelemente, die alle Zeichnungen von Windows (z <xref:System.Windows.Forms.TextBox>. b.) erledigen, werden nie Ihre <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode aufruft und verwenden daher niemals den benutzerdefinierten Code. Informationen zur Verfügbarkeit der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode finden Sie in der Hilfe Dokumentation für das jeweilige Steuerelement, das Sie ändern möchten. Eine Liste aller Windows Form-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md). Wenn ein Steuerelement nicht <xref:System.Windows.Forms.Control.OnPaint%2A> als Element Methode aufgeführt ist, können Sie seine Darstellung nicht ändern, indem Sie diese Methode überschreiben. Weitere Informationen über benutzerdefinierte Darstellung finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).

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

## <a name="see-also"></a>Siehe auch

- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)
- [Vorgehensweise: Erben von der Control-Klasse](how-to-inherit-from-the-control-class.md)
- [Vorgehensweise: Erben von der UserControl-Klasse](how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Steuerelemente für Windows Forms erstellen](how-to-author-controls-for-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
