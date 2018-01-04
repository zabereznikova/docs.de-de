---
title: "Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e72b2516efab3bc5b5d8cc7cacb66f149f3a66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 <xref:System.Windows.Forms.ToolBar>Schaltflächen können Symbole darin enthaltene zur leichteren Identifizierung von Benutzern anzuzeigen. Dies wird durch Hinzufügen von Bildern, erreicht die <xref:System.Windows.Forms.ImageList> Komponente und verknüpfen es mit der <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ToolBar> Steuerelement und ein <xref:System.Windows.Forms.ImageList> Komponente. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Um ein Symbol für eine Symbolleisten-Schaltfläche zur Entwurfszeit festgelegt.  
  
1.  Hinzufügen von Bildern, die <xref:System.Windows.Forms.ImageList> Komponente. Weitere Informationen finden Sie unter [wie: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Wählen Sie die <xref:System.Windows.Forms.ToolBar> Steuerelement auf dem Formular.  
  
3.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.ImageList%2A> Eigenschaft, um die <xref:System.Windows.Forms.ImageList> Komponente.  
  
4.  Klicken Sie auf die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.Buttons%2A> Eigenschaft, um auszuwählen, und klicken Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **ToolBarButton Auflistungs-Editor**.  
  
5.  Verwenden der **hinzufügen** Schaltfläche zum Hinzufügen von Schaltflächen auf der <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
6.  In der **Eigenschaften** im Bereich auf der rechten Seite des angezeigten Fenster die **ToolBarButton Auflistungs-Editor**legen die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> Eigenschaft jeder Symbolleisten-Schaltfläche, um einen der Werte in der Liste der gezeichnet wird, aus der Bilder, die Sie hinzugefügt, um haben die <xref:System.Windows.Forms.ImageList> Komponente.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolBar>  
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
