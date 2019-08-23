---
title: 'Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960433"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms
Mithilfe der <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft und der- <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft können Sie die Sortier-und Filterfunktion des Steuer Elements verfügbar machen. Sie können eine einfache Sortierung anwenden, wenn die zugrunde liegende Daten <xref:System.ComponentModel.IBindingList>Quelle eine ist, und Sie können Filter und erweiterte Sortierung anwenden, wenn die <xref:System.ComponentModel.IBindingListView>Datenquelle eine ist. Die <xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft erfordert die ADO.NET-Standard Syntax: eine Zeichenfolge, die den Namen einer Datenspalte in der Daten `ASC` Quelle `DESC` darstellt, gefolgt von oder, um anzugeben, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert werden soll. Sie können eine erweiterte Sortierung oder eine Sortierung mit mehreren Spalten festlegen, indem Sie jede Spalte durch ein Komma Trennzeichen trennen. Die <xref:System.Windows.Forms.BindingSource.Filter%2A> -Eigenschaft nimmt einen Zeichen folgen Ausdruck an.  
  
> [!NOTE]
> Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>So filtern Sie Daten mit der BindingSource  
  
- Legen Sie <xref:System.Windows.Forms.BindingSource.Filter%2A> die-Eigenschaft auf den gewünschten Ausdruck fest.  
  
     Im folgenden Codebeispiel ist der Ausdruck ein Spaltenname, gefolgt von dem Wert, den Sie für die Spalte benötigen.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>So sortieren Sie Daten mit der BindingSource  
  
1. Legen Sie <xref:System.Windows.Forms.BindingSource.Sort%2A> die-Eigenschaft auf den Spaltennamen fest, den `ASC` Sie `DESC` folgen möchten, oder, um den aufsteigenden oder absteigenden Auftrag anzugeben.  
  
2. Trennen Sie mehrere Spalten durch ein Komma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden Daten aus der Customers-Tabelle der Beispieldatenbank Northwind in ein <xref:System.Windows.Forms.DataGridView> -Steuerelement geladen, und die angezeigten Daten werden gefiltert und sortiert.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular ein, <xref:System.Windows.Forms.BindingSource> das `BindingSource1` ein mit <xref:System.Windows.Forms.DataGridView> dem `dataGridView1`Namen und ein mit dem Namen enthält. Behandeln Sie <xref:System.Windows.Forms.Form.Load> das-Ereignis für das Formular `InitializeSortedFilteredBindingSource` , und nennen Sie es in der Load-Ereignishandlermethode  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Vorgehensweise: Installieren von Beispiel Datenbanken](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource-Komponente](bindingsource-component.md)
