---
title: 'Vorgehensweise: Navigieren Sie durch Daten in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 0d3703019f081f07ecb29bf9229f0a2044764ae6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586903"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Vorgehensweise: Navigieren Sie durch Daten in Windows Forms
In einer Windows-Anwendung ist die einfachste Möglichkeit zum Navigieren durch Datensätze in einer Datenquelle zum Binden einer <xref:System.Windows.Forms.BindingSource> -Komponente an die Datenquelle und dann Binden von Steuerelementen an die <xref:System.Windows.Forms.BindingSource>. Anschließend können Sie die integrierte Navigationsmethode auf die <xref:System.Windows.Forms.BindingSource> solche eine <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> und <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Mit diesen Methoden wird angepasst, die <xref:System.Windows.Forms.BindingSource.Position%2A> und <xref:System.Windows.Forms.BindingSource.Current%2A> Eigenschaften der <xref:System.Windows.Forms.BindingSource> entsprechend. Können Sie auch auf ein Element stoßen und es als aktuelles Element festlegen, durch Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Erhöht die Position in einer Datenquelle  
  
1.  Legen Sie die <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft der <xref:System.Windows.Forms.BindingSource> für die gebundenen Daten auf die Position des Datensatzes zu wechseln. Das folgende Beispiel veranschaulicht die Verwendung der <xref:System.Windows.Forms.BindingSource.MoveNext%2A> -Methode der der <xref:System.Windows.Forms.BindingSource> zur Erhöhung der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft bei der `nextButton` geklickt wird. Die <xref:System.Windows.Forms.BindingSource> zugeordnet ist die `Customers` Tabelle eines Datasets `Northwind`.  
  
    > [!NOTE]
    >  Festlegen der <xref:System.Windows.Forms.BindingSource.Position%2A> Eigenschaft auf einen Wert nach der ersten oder letzten Datensatz führt nicht zu einem Fehler wie der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] lässt nicht die Position auf einen Wert außerhalb der Grenzen der Liste festlegen. Wenn es ist wichtig für Ihre Anwendung aus, um herauszufinden, ob Sie nach der ersten oder letzten Datensatz gelesen haben, enthalten Sie eine Logik zum Überprüfen, ob Sie die Anzahl der Elemente überschreitet.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Überprüft, ob Sie am Ende oder Anfang bestanden haben  
  
1.  Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.BindingSource.PositionChanged>-Ereignis. In den Handler auf können Sie testen, ob der vorgeschlagenen Positionswert die Anzahl der tatsächlichen Daten überschritten hat.  
  
     Im folgende Beispiel wird veranschaulicht, wie Sie testen können, ob Sie das letzte Datenelement erreicht haben. Im Beispiel, wenn Sie das letzte Element sind die **Weiter** Formular auf die Schaltfläche ist deaktiviert.  
  
    > [!NOTE]
    >  Beachten Sie, dass, sollten Sie die Liste, die Sie im Code navigieren ändern, müssen Sie erneut aktivieren die **Weiter** Schaltfläche, damit die Benutzer die gesamte Dauer der neuen Liste durchsuchen können. Achten Sie außerdem, die den oben genannten <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignis für den jeweiligen <xref:System.Windows.Forms.BindingSource> Sie arbeiten mit seiner Ereignisbehandlungsmethode verknüpft sein muss. Folgendes ist ein Beispiel für eine Methode zur Behandlung der <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignis:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Zum Auffinden eines Elements, und legen Sie es als aktuelles Element  
  
1.  Suchen Sie den Datensatz, die, den Sie als das aktuelle Element festlegen möchten. Hierzu können Sie mithilfe der <xref:System.Windows.Forms.BindingSource.Find%2A> Methode der <xref:System.Windows.Forms.BindingSource>, wenn die Datenquelle implementiert <xref:System.ComponentModel.IBindingList>. Einige Beispiele für Daten, Datenquellen, die implementieren <xref:System.ComponentModel.IBindingList> sind <xref:System.ComponentModel.BindingList%601> und <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- [Von Windows Forms unterstützte Datenquellen](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
- [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
