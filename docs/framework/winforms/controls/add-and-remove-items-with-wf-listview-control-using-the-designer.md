---
title: "Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c5000df10504c3dc0aad7950cdbe82fd53bc1c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers
Beim Hinzufügen eines Elements zu einem Windows Forms <xref:System.Windows.Forms.ListView> -Steuerelement besteht aus in erster Linie das Element angeben und Eigenschaften zuweisen. Hinzufügen oder Entfernen von Listenelementen kann zu einem beliebigen Zeitpunkt erfolgen.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-items-using-the-designer"></a>Hinzufügen oder Entfernen von Elementen mithilfe des Designers  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ListView>-Steuerelement.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf die **Auslassungszeichen** (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft.  
  
     Die **ListViewItem Auflistungs-Editor** angezeigt wird.  
  
3.  Um ein Element hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften des neuen Elements festlegen, wie z. B. die <xref:System.Windows.Forms.ListView.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> Eigenschaften.  
  
4.  Um ein Element zu entfernen, wählen Sie ihn aus, und klicken Sie auf die **entfernen** Schaltfläche.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
