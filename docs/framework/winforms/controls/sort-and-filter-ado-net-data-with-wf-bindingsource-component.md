---
title: 'Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms'
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
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46947e314394d56b5ef0439f33910bb493012db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms
Sie können das Sortieren und Filtern von Funktion verfügbar machen <xref:System.Windows.Forms.BindingSource> steuern, über die <xref:System.Windows.Forms.BindingSource.Sort%2A> und <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaften. Können Sie anwenden, einfache Sortierung, wenn die zugrunde liegenden Datenquelle ist ein <xref:System.ComponentModel.IBindingList>, und Sie können Filter anzuwenden und erweiterte Sortierung, wenn die Datenquelle ist ein <xref:System.ComponentModel.IBindingListView>. Die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft erfordert Standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Syntax: eine Zeichenfolge, die den Namen einer Spalte mit Daten in der Datenquelle, gefolgt von `ASC` oder `DESC` , um anzugeben, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert werden sollen. Sie können erweiterte Sortierung oder mehrere Spalten zu sortieren, indem Sie jede Spalte durch ein Komma als Trennzeichen trennen festlegen. Die <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft akzeptiert einen Zeichenfolgenausdruck.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>So filtern Sie Daten mit der BindingSource-Komponente  
  
-   Legen Sie die <xref:System.Windows.Forms.BindingSource.Filter%2A> -Eigenschaft auf die gewünschte Ausdruck.  
  
     Im folgenden Codebeispiel wird der Ausdruck einen Spaltennamen, gefolgt vom Wert, der für die Spalte.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>So sortieren Sie Daten mit der BindingSource-Komponente  
  
1.  Legen Sie die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft, um den gewünschten gefolgt von Spaltennamen `ASC` oder `DESC` an, dass die aufsteigende oder absteigende Reihenfolge.  
  
2.  Mehrere Spalten mit einem Komma getrennt werden.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel lädt Daten aus der Customers-Tabelle der Northwind-Beispieldatenbank in einem <xref:System.Windows.Forms.DataGridView> zu steuern, gefiltert und sortiert die angezeigten Daten.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular, enthält ein <xref:System.Windows.Forms.BindingSource> mit dem Namen `BindingSource1` und ein <xref:System.Windows.Forms.DataGridView> mit dem Namen `dataGridView1`. Behandeln der <xref:System.Windows.Forms.Form.Load> -Ereignis für das Formular, und rufen `InitializeSortedFilteredBindingSource` in den Load-Ereignishandlermethode.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [Gewusst wie: Installieren von Beispieldatenbanken](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)
