---
title: 'Vorgehensweise: Navigieren durch Daten in Windows Forms'
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
ms.openlocfilehash: eb973497f51592b5d34c22e62da77612aec23c35
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964274"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Vorgehensweise: Navigieren durch Daten in Windows Forms
In einer Windows-Anwendung ist die einfachste Möglichkeit zum Navigieren durch Datensätze in einer Datenquelle das Binden <xref:System.Windows.Forms.BindingSource> einer Komponente an die Datenquelle und das anschließende Binden von <xref:System.Windows.Forms.BindingSource>Steuerelementen an die. Anschließend können Sie die integrierte Navigations <xref:System.Windows.Forms.BindingSource> Methode für <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> und <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>verwenden. Wenn Sie diese Methoden verwenden, <xref:System.Windows.Forms.BindingSource.Position%2A> werden <xref:System.Windows.Forms.BindingSource.Current%2A> die-Eigenschaft <xref:System.Windows.Forms.BindingSource> und die-Eigenschaft der entsprechend angepasst. Sie können ein Element auch suchen und als Aktuelles Element festlegen, indem Sie die <xref:System.Windows.Forms.BindingSource.Position%2A> -Eigenschaft festlegen.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>So erhöhen Sie die Position in einer Datenquelle  
  
1. Legen Sie <xref:System.Windows.Forms.BindingSource.Position%2A> die-Eigenschaft <xref:System.Windows.Forms.BindingSource> des-Objekts für die gebundenen Daten auf die Daten Satz Position fest, an die Sie gelangen. Das folgende Beispiel veranschaulicht die Verwendung <xref:System.Windows.Forms.BindingSource.MoveNext%2A> der-Methode <xref:System.Windows.Forms.BindingSource> von, um die <xref:System.Windows.Forms.BindingSource.Position%2A> -Eigenschaft zu `nextButton` erhöhen, wenn auf das geklickt wird. Der <xref:System.Windows.Forms.BindingSource> ist der `Customers` Tabelle eines Datasets `Northwind`zugeordnet.  
  
    > [!NOTE]
    > Das Festlegen <xref:System.Windows.Forms.BindingSource.Position%2A> der-Eigenschaft auf einen Wert, der über den ersten oder letzten Datensatz hinausgeht, führt nicht zu einem Fehler, da das .NET Framework nicht zulässt, dass die Position auf einen Wert außerhalb der Grenzen der Liste festgelegt wird. Wenn es in Ihrer Anwendung wichtig ist, zu wissen, ob Sie den ersten oder letzten Datensatz verlassen haben, schließen Sie die Logik ein, um zu testen, ob die Datenelement Anzahl überschritten wird.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>So überprüfen Sie, ob Sie das Ende oder den Anfang überschritten haben  
  
1. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.BindingSource.PositionChanged>-Ereignis. Im-Handler können Sie testen, ob der vorgeschlagene Positionswert die tatsächliche Datenelement Anzahl überschritten hat.  
  
     Im folgenden Beispiel wird veranschaulicht, wie Sie testen können, ob Sie das letzte Datenelement erreicht haben. Wenn Sie im Beispiel das letzte Element haben, wird die Schaltfläche **weiter** im Formular deaktiviert.  
  
    > [!NOTE]
    > Wenn Sie die Liste ändern möchten, die Sie im Code navigieren, sollten Sie die Schaltfläche **weiter** aktivieren, damit Benutzer die gesamte Länge der neuen Liste durchsuchen können. Beachten Sie außerdem, dass das oben <xref:System.Windows.Forms.BindingSource.PositionChanged> beschriebene Ereignis für den <xref:System.Windows.Forms.BindingSource> spezifischen, mit dem Sie arbeiten, mit seiner Ereignis Behandlungsmethode verknüpft werden muss. Im folgenden finden Sie ein Beispiel für eine Methode zur Behandlung <xref:System.Windows.Forms.BindingSource.PositionChanged> des-Ereignisses:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>So suchen Sie ein Element und legen es als Aktuelles Element fest  
  
1. Suchen Sie den Datensatz, den Sie als Aktuelles Element festlegen möchten. Dies können Sie mithilfe der <xref:System.Windows.Forms.BindingSource.Find%2A> -Methode <xref:System.Windows.Forms.BindingSource>der tun, wenn Ihre Datenquelle implementiert <xref:System.ComponentModel.IBindingList>. Einige Beispiele für Datenquellen, die <xref:System.ComponentModel.IBindingList> implementieren <xref:System.ComponentModel.BindingList%601> , <xref:System.Data.DataView>sind und.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Von Windows Forms unterstützte Datenquellen](data-sources-supported-by-windows-forms.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
