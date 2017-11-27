---
title: "Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8df87e62e8c19ee6e30ffdbc2a4e473b444f538
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms
In der Detailansicht der <xref:System.Windows.Forms.ListView> -Steuerelement kann mehrere Spalten für jedes Listenelement anzeigen. Die Spalten können Sie für den Benutzer verschiedene Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise konnte eine Liste der Dateien angezeigt, die Dateinamen, Dateityp, Größe und das Datum, an der letzten der Datei Änderung. Informationen zum Auffüllen der Spalten aus, nachdem sie erstellt wurden, finden Sie unter [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>So fügen Sie Spalten programmgesteuert hinzu  
  
1.  Legen Sie das Steuerelement <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft <xref:System.Windows.Forms.View.Details>.  
  
2.  Verwenden der <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> Methode der Listenansicht <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
