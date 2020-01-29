---
title: Erstellen einer Multipane-Benutzeroberfläche mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 6b41d538f1cd1633cec51c89e27adf3c5b47f9a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737278"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms mithilfe des Designers
Im folgenden Verfahren erstellen Sie eine Multipane-Benutzeroberfläche, die der in Microsoft Outlook verwendeten Benutzeroberfläche mit einer **Ordner** Liste **, einem** Meldungs Bereich und einem **Vorschau** Bereich ähnelt. Diese Anordnung wird hauptsächlich durch Andocken von Steuerelementen im Formular erreicht.

 Wenn Sie ein Steuerelement andocken, legen Sie fest, an welchen Rand des übergeordneten Containers ein Steuerelement angedockt ist. Wenn Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Right>festlegen, wird der Rechte Rand des Steuer Elements an den rechten Rand des übergeordneten Steuer Elements angedockt. Außerdem wird die Größe des angedockten Randes des Steuer Elements geändert, sodass es mit dem des zugehörigen Container Steuer Elements identisch ist. Weitere Informationen zur Funktionsweise der <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft finden Sie unter Gewusst [wie: Andocken von Steuerelementen auf Windows Forms](how-to-dock-controls-on-windows-forms.md).

 Dieses Verfahren konzentriert sich auf das Anordnen der <xref:System.Windows.Forms.SplitContainer> und der anderen Steuerelemente im Formular, nicht auf das Hinzufügen von Funktionen, damit die Anwendung Microsoft Outlook imitiert.

 Um diese Benutzeroberfläche zu erstellen, platzieren Sie alle Steuerelemente in einem <xref:System.Windows.Forms.SplitContainer>-Steuerelement, das ein <xref:System.Windows.Forms.TreeView>-Steuerelement im linken Bereich enthält. Der Rechte Bereich des <xref:System.Windows.Forms.SplitContainer> Steuer Elements enthält ein zweites <xref:System.Windows.Forms.SplitContainer> Steuerelement mit einem <xref:System.Windows.Forms.ListView>-Steuerelement oberhalb eines <xref:System.Windows.Forms.RichTextBox> Steuer Elements. Diese <xref:System.Windows.Forms.SplitContainer> Steuerelemente ermöglichen eine unabhängige Größe der anderen Steuerelemente im Formular. Sie können die Techniken in diesem Verfahren anpassen, um eigene benutzerdefinierte Benutzeroberflächen zu erstellen.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>So erstellen Sie eine Benutzeroberfläche im Outlook-Stil zur Entwurfszeit

1. Erstellen Sie ein neues Windows-Anwendungsprojekt (**Datei** > **Neues** > **Projekt** >  **C# Visual** oder **Visual Basic** > **klassischen Desktop** > **Windows Forms Anwendung**).

2. Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer>-Steuerelement aus der **Toolbox** auf das Formular. Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Dock%2A> auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

3. Ziehen Sie ein <xref:System.Windows.Forms.TreeView>-Steuerelement aus der **Toolbox** in den linken Bereich des <xref:System.Windows.Forms.SplitContainer> Steuer Elements. Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Left> fest, indem Sie auf den linken Bereich im Wert-Editor klicken, der angezeigt wird, wenn auf den Pfeil nach unten geklickt wird.

4. Ziehen Sie ein weiteres <xref:System.Windows.Forms.SplitContainer> Steuerelement aus der **Toolbox**. Platzieren Sie Sie im rechten Bereich des <xref:System.Windows.Forms.SplitContainer> Steuer Elements, das Sie dem Formular hinzugefügt haben. Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.SplitContainer.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> und die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Orientation%2A> auf <xref:System.Windows.Forms.Orientation.Horizontal>fest.

5. Ziehen Sie ein <xref:System.Windows.Forms.ListView>-Steuerelement aus der **Toolbox** in den oberen Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Steuer Elements, das Sie dem Formular hinzugefügt haben. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft des <xref:System.Windows.Forms.ListView> -Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

6. Ziehen Sie ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement aus der **Toolbox** auf den unteren Bereich des zweiten <xref:System.Windows.Forms.SplitContainer> Steuer Elements. Legen Sie die <xref:System.Windows.Forms.SplitContainer.Dock%2A> -Eigenschaft des <xref:System.Windows.Forms.RichTextBox> -Steuerelements auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

     Wenn Sie an diesem Punkt F5 drücken, um die Anwendung auszuführen, zeigt das Formular eine dreiteilige Benutzeroberfläche ähnlich der von Microsoft Outlook an.

    > [!NOTE]
    > Wenn Sie den Mauszeiger über einen der Aufteilungen innerhalb der <xref:System.Windows.Forms.SplitContainer> Steuerelemente bewegen, können Sie die Größe der internen Dimensionen ändern.

An dieser Stelle der Anwendungsentwicklung haben Sie eine ausgereifte Benutzeroberfläche entwickelt. Der nächste Schritt ist das Fortsetzen der Programmierung der Anwendung selbst, indem das <xref:System.Windows.Forms.TreeView> Steuerelement und <xref:System.Windows.Forms.ListView> Steuerelemente mit einer Art von Datenquelle verbunden werden. Weitere Informationen zum Verbinden von Steuerelementen mit Daten finden Sie unter [Datenbindung und Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
