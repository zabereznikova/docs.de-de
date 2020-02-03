---
title: Hinzufügen von Spalten zum ListView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744584"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms
In der Detailansicht kann das <xref:System.Windows.Forms.ListView>-Steuerelement mehrere Spalten für jedes Listenelement anzeigen. Sie können die Spalten verwenden, um dem Benutzer mehrere Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise können in einer Liste mit Dateien der Dateiname, Dateityp, die Größe und das Datum der letzten Änderung der Datei angezeigt werden. Informationen zum Auffüllen der Spalten nach ihrer Erstellung finden Sie unter Gewusst [wie: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuer](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)Element.  
  
### <a name="to-add-columns-programmatically"></a>So fügen Sie Spalten Programm gesteuert hinzu  
  
1. Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft des Steuer Elements auf <xref:System.Windows.Forms.View.Details>fest.  
  
2. Verwenden Sie die <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ListView.Columns%2A>-Eigenschaft der Listenansicht.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ListView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
