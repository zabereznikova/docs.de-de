---
title: "Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27d7c2cf607f463871862fbac373a88d2cda028e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Standardmäßig können Benutzer ändern, Text und numerischen Daten, die in Windows Forms angezeigten <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn Sie Daten anzeigen, der nicht zum ändern möchten, müssen Sie die Spalten, mit den Daten schreibgeschützt. Informationen dazu, wie Sie das Steuerelement vollständig schreibgeschützt machen, finden Sie unter [wie: verhindern Hinzufügens und Löschens in der Windows Forms DataGridView-Steuerelement mithilfe des Designers](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>Um eine Spalte schreibgeschützt machen, indem Sie mithilfe des Designers  
  
1.  Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.  
  
2.  Wählen Sie eine Spalte aus der **ausgewählte Spalten** Liste.  
  
3.  In der **Spalteneigenschaften** Raster Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> Eigenschaft `true`.  
  
    > [!NOTE]
    >  Sie können auch eine Spalte nur-Lese beim machen Sie ihn dazu hinzufügen der **Read Only** Kontrollkästchen in der **Add Column** (Dialogfeld).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
