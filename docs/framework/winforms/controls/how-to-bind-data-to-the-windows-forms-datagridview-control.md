---
title: 'Vorgehensweise: Datenbindung in Windows Forms-DataGridView-Steuerelement'
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e147109a64687177f201ad1e312fab56ea61d604
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160069"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Vorgehensweise: Datenbindung in Windows Forms-DataGridView-Steuerelement

Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt die standardmäßige Windows Forms-Datenbindungsmodell verwendet, damit es mit einer Vielzahl von Datenquellen gebunden werden kann. In der Regel Sie binden an eine <xref:System.Windows.Forms.BindingSource> , verwaltet die Interaktion mit der Datenquelle. Die <xref:System.Windows.Forms.BindingSource> kann jede beliebige Windows Forms-Datenquelle, die Ihnen viel Flexibilität bei der Auswahl oder Änderung des Daten Speicherorts bietet sein. Weitere Informationen zu den Datenquellen der <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt, finden Sie die [Übersicht über das DataGridView-Steuerelement](datagridview-control-overview-windows-forms.md).  

Visual Studio bietet umfassende Unterstützung für die Datenbindung an das DataGridView-Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an das Windows Forms-DataGridView-Steuerelement, das mithilfe des Designers](bind-data-to-the-datagrid-using-the-designer.md).  

So verbinden ein DataGridView-Steuerelement mit Daten:

1. Implementieren Sie eine Methode, um die Details zum Abrufen der Daten zu behandeln. Das folgende Codebeispiel implementiert eine `GetData` -Methode, initialisiert ein <xref:System.Data.SqlClient.SqlDataAdapter>, und verwendet ihn zum Auffüllen einer <xref:System.Data.DataTable>. Klicken Sie dann bindet die <xref:System.Data.DataTable> auf die <xref:System.Windows.Forms.BindingSource>. 

2. Des Formulars <xref:System.Windows.Forms.Form.Load> Ereignishandler, binden die <xref:System.Windows.Forms.DataGridView> die Steuerung an die <xref:System.Windows.Forms.BindingSource>, und rufen Sie die `GetData` Methode zum Abrufen der Daten.  

## <a name="example"></a>Beispiel

Dieser vollständige Codebeispiel ruft Daten ab, aus einer Datenbank in einem DataGridView-Steuerelement in einem Windows-Formular zu füllen. Das Formular verfügt auch über die Schaltflächen zum Laden von Daten und Übermitteln von Änderungen an der Datenbank.  

Für dieses Beispiel benötigen Sie Folgendes: 

- Zugriff mit der Beispieldatenbank Northwind-SQL Server. Weitere Informationen zum Installieren der Beispieldatenbank Northwind finden Sie unter [erhalten Sie die Beispieldatenbanken ADO.NET Codebeispiele](../../data/adonet/sql/linq/downloading-sample-databases.md). 

- Verweise auf die Assemblys System, "System.Windows.Forms", "System.Data" und "System.xml".  

Fügen Sie zum Erstellen und dieses Beispiel ausführen, die den Code in die *Form1* Codedatei in einem neuen Windows Forms-Projekt. Informationen zum Erstellen von der C# oder Visual Basic über die Befehlszeile, finden Sie unter [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Füllen Sie die `connectionString` Variable im Beispiel durch die Werte für Ihre Beispieldatenbank Northwind-SQL Server-Verbindung. Windows-Authentifizierung, integrierte Sicherheit, so genannte ist eine sicherere Methode für die Verbindung mit der Datenbank als ein Kennwort in der Verbindungszeichenfolge speichern. Weitere Informationen zur verbindungssicherheit finden Sie unter [Schützen von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten in Windows Forms-DataGridView-Steuerelement](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Schützen von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md)
