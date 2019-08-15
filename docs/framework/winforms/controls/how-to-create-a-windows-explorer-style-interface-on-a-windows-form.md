---
title: 'Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: db2c5431dfb0156c1508a18ef13d2af80eb4981b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039533"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms
Windows Explorer ist eine gängige Benutzeroberfläche für Anwendungen.

 Windows-Explorer ist im Grunde genommen <xref:System.Windows.Forms.TreeView> ein Steuerelement <xref:System.Windows.Forms.ListView> und ein Steuerelement in separaten Bereichen. Die Größe der Panels wird durch einen Splitter geändert. Diese Anordnung von Steuerelementen ist sehr effektiv zum Anzeigen und Durchsuchen von Informationen.

 In den folgenden Schritten wird gezeigt, wie Steuerelemente in einem Windows-Explorer-ähnlichen Formular angeordnet werden. Sie zeigen nicht, wie Sie die Dateibrowser Funktionalität der Windows Explorer-Anwendung hinzufügen.

## <a name="to-create-a-windows-explorer-style-windows-form"></a>So erstellen Sie ein Windows-Formular im Windows-Explorer

1. Erstellen eines neuen Windows-Anwendungs Projekts (**Datei** > "**Neues** > **Projekt** > **C#** " oder **Visual Basic** > **klassischem Desktop**  >  **Windows Forms Anwendung**).

2. Aus der **Toolbox**:

    1. Ziehen Sie <xref:System.Windows.Forms.SplitContainer> ein-Steuerelement auf das Formular.

    2. Ziehen Sie <xref:System.Windows.Forms.TreeView> ein-Steuerelement in **SplitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> der Bereich des-Steuer Elements, das als **Panel1**gekennzeichnet ist)

    3. Ziehen Sie <xref:System.Windows.Forms.ListView> ein-Steuerelement in **SplitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> der Bereich des-Steuer Elements, das als **Panel2**gekennzeichnet ist)

3. Wählen Sie alle drei Steuerelemente aus, indem Sie die STRG-Taste gedrückt halten und darauf klicken. Wenn Sie das <xref:System.Windows.Forms.SplitContainer> Steuerelement auswählen, klicken Sie auf die Splitter Leiste anstelle der Panels.

    > [!NOTE]
    >  Verwenden Sie nicht den Befehl **Alle auswählen** im Menü **Bearbeiten** . Wenn Sie dies tun, wird die im nächsten Schritt benötigte Eigenschaft nicht im **Eigenschaften** Fenster angezeigt.

4. Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Dock%2A> auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

5. Drücken Sie F5, um die Anwendung auszuführen.

     Das Formular zeigt eine zweiteilige Benutzeroberfläche an, ähnlich der von Windows Explorer.

    > [!NOTE]
    >  Wenn Sie den Splitter ziehen, ändert sich die Größe der Panels.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- [Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Vorgehensweise: Definieren des Verhaltens der Größenänderung und Positionierung in einem geteilten Fenster](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Vorgehensweise: Fenster horizontal aufteilen](how-to-split-a-window-horizontally.md)
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
