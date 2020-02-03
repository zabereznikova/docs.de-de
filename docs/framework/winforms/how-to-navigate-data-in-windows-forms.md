---
title: 'Gewusst wie: Navigieren in Daten'
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
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739401"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Gewusst wie: Navigieren durch Daten in Windows Forms
In einer Windows-Anwendung ist die einfachste Möglichkeit zum Navigieren durch Datensätze in einer Datenquelle das Binden einer <xref:System.Windows.Forms.BindingSource> Komponente an die Datenquelle und das anschließende Binden von Steuerelementen an die <xref:System.Windows.Forms.BindingSource>. Anschließend können Sie die integrierte Navigations Methode auf dem <xref:System.Windows.Forms.BindingSource> wie <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> und <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>verwenden. Durch die Verwendung dieser Methoden werden die <xref:System.Windows.Forms.BindingSource.Position%2A>-und <xref:System.Windows.Forms.BindingSource.Current%2A> Eigenschaften der <xref:System.Windows.Forms.BindingSource> entsprechend angepasst. Sie können ein Element auch suchen und als Aktuelles Element festlegen, indem Sie die <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft festlegen.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>So erhöhen Sie die Position in einer Datenquelle  
  
1. Legen Sie die <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft des <xref:System.Windows.Forms.BindingSource> für die gebundenen Daten auf die Daten Satz Position fest, auf die Sie gelangen. Das folgende Beispiel veranschaulicht die Verwendung der <xref:System.Windows.Forms.BindingSource.MoveNext%2A>-Methode des <xref:System.Windows.Forms.BindingSource>, um die <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft zu erhöhen, wenn auf das `nextButton` geklickt wird. Der <xref:System.Windows.Forms.BindingSource> ist mit der `Customers` Tabelle eines Datasets `Northwind`verknüpft.  
  
    > [!NOTE]
    > Wenn Sie die <xref:System.Windows.Forms.BindingSource.Position%2A>-Eigenschaft auf einen Wert über den ersten oder letzten Datensatz festlegen, führt dies nicht zu einem Fehler, da das .NET Framework nicht zulässt, dass die Position auf einen Wert außerhalb der Grenzen der Liste festgelegt wird. Wenn es in Ihrer Anwendung wichtig ist, zu wissen, ob Sie den ersten oder letzten Datensatz verlassen haben, schließen Sie die Logik ein, um zu testen, ob die Datenelement Anzahl überschritten wird.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>So überprüfen Sie, ob Sie das Ende oder den Anfang überschritten haben  
  
1. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.BindingSource.PositionChanged>-Ereignis. Im-Handler können Sie testen, ob der vorgeschlagene Positionswert die tatsächliche Datenelement Anzahl überschritten hat.  
  
     Im folgenden Beispiel wird veranschaulicht, wie Sie testen können, ob Sie das letzte Datenelement erreicht haben. Wenn Sie im Beispiel das letzte Element haben, wird die Schaltfläche **weiter** im Formular deaktiviert.  
  
    > [!NOTE]
    > Wenn Sie die Liste ändern möchten, die Sie im Code navigieren, sollten Sie die Schaltfläche **weiter** aktivieren, damit Benutzer die gesamte Länge der neuen Liste durchsuchen können. Beachten Sie außerdem, dass die oben genannten <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignis für die jeweilige <xref:System.Windows.Forms.BindingSource>, mit der Sie arbeiten, mit der Ereignis Behandlungsmethode verknüpft werden müssen. Im folgenden finden Sie ein Beispiel für eine Methode zum Behandeln des <xref:System.Windows.Forms.BindingSource.PositionChanged> Ereignisses:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>So suchen Sie ein Element und legen es als Aktuelles Element fest  
  
1. Suchen Sie den Datensatz, den Sie als Aktuelles Element festlegen möchten. Dies können Sie mit der <xref:System.Windows.Forms.BindingSource.Find%2A>-Methode des <xref:System.Windows.Forms.BindingSource>tun, wenn die Datenquelle <xref:System.ComponentModel.IBindingList>implementiert. Einige Beispiele für Datenquellen, die <xref:System.ComponentModel.IBindingList> implementieren, sind <xref:System.ComponentModel.BindingList%601> und <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Von Windows Forms unterstützte Datenquellen](data-sources-supported-by-windows-forms.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
