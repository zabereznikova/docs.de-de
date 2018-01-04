---
title: "Gewusst wie: Erstellen einer Oberfläche im Stil von Windows Explorer in einem Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c30dd18e7303cf9fe913760da3f9dad7bca3c95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Gewusst wie: Erstellen einer Oberfläche im Stil von Windows Explorer in einem Windows Form
Windows-Explorer wird eine gemeinsame Benutzeroberfläche Wahl für Anwendungen aufgrund seiner Kenntnisse in bereit.  
  
 Windows-Explorer ist im Wesentlichen eine <xref:System.Windows.Forms.TreeView> Steuerelement und ein <xref:System.Windows.Forms.ListView> Steuerelement auf separate Bereiche. Die Bereiche sind durch eine Trennleiste in der Größe veränderbaren vorgenommen. Diese Anordnung von Steuerelementen ist sehr gut für die Anzeige und das Durchsuchen von Informationen.  
  
 Die folgenden Schritte zeigen, wie zum Anordnen von Steuerelementen in einer Windows-Explorer-ähnlichen Format. Enthalten sie die Datei durchsuchen Funktionalität von Windows Explorer-Anwendung hinzufügen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>So erstellen ein Windows Explorer-ähnliche Windows Form  
  
1.  Erstellen Sie ein neues Windows-Anwendungsprojekt. Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Aus der **Toolbox**:  
  
    1.  Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> Steuerelement auf das Formular.  
  
    2.  Ziehen Sie eine <xref:System.Windows.Forms.TreeView> steuern in **SplitterPanel1** (der Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement markiert **Panel1**).  
  
    3.  Ziehen Sie eine <xref:System.Windows.Forms.ListView> steuern in **SplitterPanel2** (der Bereich des der <xref:System.Windows.Forms.SplitContainer> Steuerelement markiert **Panel2**).  
  
3.  Wählen Sie alle drei Steuerelemente, indem Sie die STRG-Taste drücken, und klicken sie dann auf. Bei Auswahl der <xref:System.Windows.Forms.SplitContainer> steuern, und klicken Sie auf die Teilerleiste, anstatt die Bereiche.  
  
    > [!NOTE]
    >  Verwenden Sie nicht die **Alles markieren** Befehl die **bearbeiten** Menü. In diesem Fall die Eigenschaft, die im nächsten Schritt benötigt erscheint nicht der **Eigenschaften** Fenster.  
  
4.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Drücken Sie F5, um die Anwendung auszuführen.  
  
     Das Formular zeigt eine zweiteilige Benutzeroberfläche ähnelt der von der Windows-Explorer.  
  
    > [!NOTE]
    >  Wenn Sie den Splitter ziehen, Größe der Bereiche selbst ändern.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 [Gewusst wie: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [Gewusst wie: Horizontales Teilen eines Fensters](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
