---
title: 'Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 578fdf8e24803db0e0d80ff22aa5cebebbc2663e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616000"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Vorgehensweise: Erstellen einer Oberfläche im Stil von Windows Explorer in Windows Forms
Windows-Explorer ist eine gemeinsame Benutzeroberfläche Wahl für Anwendungen aufgrund seiner Kenntnisse bereit.  
  
 Windows-Explorer ist im Wesentlichen eine <xref:System.Windows.Forms.TreeView> Steuerelement und ein <xref:System.Windows.Forms.ListView> Steuerelement auf separate Bereiche. Die Bereiche werden durch eine Aufteilung in der Größe veränderbaren vorgenommen. Diese Anordnung von Steuerelementen ist sehr gut für anzeigen und Durchsuchen von Informationen.  
  
 Die folgenden Schritte zeigen, wie Steuerelemente in einem Windows-Explorer-ähnlichen Format angeordnet wird. Sie sind nicht zum Hinzufügen der Funktion zum Durchsuchen von Datei, der die Windows-Explorer-Anwendung erläutert.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Um ein Windows-Formular in Windows Explorer-Stil zu erstellen.  
  
1. Erstellen Sie ein neues Windows-Anwendungsprojekt (**Datei** > **neu** > **Projekt** > **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2. Von der **Toolbox**:  
  
    1. Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> Steuerelement auf das Formular.  
  
    2. Ziehen Sie eine <xref:System.Windows.Forms.TreeView> steuern in **SplitterPanel1** (der Bereich von der <xref:System.Windows.Forms.SplitContainer> Steuerelemente **Panel1**).  
  
    3. Ziehen Sie eine <xref:System.Windows.Forms.ListView> steuern in **SplitterPanel2** (der Bereich von der <xref:System.Windows.Forms.SplitContainer> Steuerelemente **Panel2**).  
  
3. Wählen Sie alle drei Steuerelemente, indem Sie die STRG-Taste drücken, und klicken sie dann auf. Bei der Auswahl der <xref:System.Windows.Forms.SplitContainer> Steuerelement, klicken Sie auf die Teilerleiste, anstatt die Bereiche.  
  
    > [!NOTE]
    >  Verwenden Sie nicht die **Alles markieren** Befehl die **bearbeiten** Menü. Wenn Sie dies tun, die Eigenschaft, die in den nächsten Schritt erforderlich sind, erscheinen nicht im der **Eigenschaften** Fenster.  
  
4. Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.SplitContainer.Dock%2A> auf <xref:System.Windows.Forms.DockStyle.Fill>fest.  
  
5. Drücken Sie F5, um die Anwendung auszuführen.  
  
     Das Formular zeigt eine mit dem zweiteiligen Benutzeroberfläche ähnelt der von der Windows-Explorer.  
  
    > [!NOTE]
    >  Wenn Sie den Splitter ziehen, Größe der Panels selbst.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- [Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Vorgehensweise: Definieren des Größen- und Positionsänderungen Verhalten in einem geteilten Fenster](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Vorgehensweise: Horizontales Teilen eines Fensters](how-to-split-a-window-horizontally.md)
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
