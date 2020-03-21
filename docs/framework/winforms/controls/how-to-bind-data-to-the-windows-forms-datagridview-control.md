---
title: Binden von Daten an DataGridView Control
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182278"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Gewusst wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement

Das <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt das standardmäßige Windows Forms-Datenbindungsmodell, sodass es an eine Vielzahl von Datenquellen binden kann. Normalerweise binden Sie <xref:System.Windows.Forms.BindingSource> eine Bindung an eine, die die Interaktion mit der Datenquelle verwaltet. Die <xref:System.Windows.Forms.BindingSource> kann eine beliebige Windows Forms-Datenquelle sein, was Ihnen große Flexibilität bei der Auswahl oder Änderung des Speicherorts Ihrer Daten bietet. Weitere Informationen zu Datenquellen, die das <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt, finden Sie in der [DataGridView-Steuerelementübersicht](datagridview-control-overview-windows-forms.md).  

Visual Studio bietet umfassende Unterstützung für die Datenbindung an das DataGridView-Steuerelement. Weitere Informationen finden Sie unter [Gewusst wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement mithilfe des Designers](bind-data-to-the-datagrid-using-the-designer.md).  

So verbinden Sie ein DataGridView-Steuerelement mit Daten:

1. Implementieren Sie eine Methode, um die Details zum Abrufen der Daten zu behandeln. Im folgenden Codebeispiel `GetData` wird eine Methode <xref:System.Data.SqlClient.SqlDataAdapter>implementiert, die eine initialisiert <xref:System.Data.DataTable>und zum Auffüllen einer verwendet. Es bindet dann <xref:System.Data.DataTable> die <xref:System.Windows.Forms.BindingSource>an die .

2. Binden Sie das <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> Steuerelement im Ereignishandler <xref:System.Windows.Forms.BindingSource>des Formulars `GetData` an die , und rufen Sie die Methode zum Abrufen der Daten auf.  

## <a name="example"></a>Beispiel

In diesem vollständigen Codebeispiel werden Daten aus einer Datenbank abgerufen, um ein DataGridView-Steuerelement in einem Windows-Formular aufzufüllen. Das Formular verfügt auch über Schaltflächen zum erneuten Laden von Daten und Zum Übermitteln von Änderungen an die Datenbank.  

Für dieses Beispiel benötigen Sie Folgendes:

- Zugriff auf eine Northwind SQL Server-Beispieldatenbank. Weitere Informationen zum Installieren der Northwind-Beispieldatenbank finden Sie unter [Abrufen der Beispieldatenbanken für ADO.NET Codebeispiele](../../data/adonet/sql/linq/downloading-sample-databases.md).

- Verweise auf die Assemblys System,Windows.Forms, System.Data und System.Xml.  

Um dieses Beispiel zu erstellen und auszuführen, fügen Sie den Code in die *Form1-Codedatei* in einem neuen Windows Forms-Projekt ein. Informationen zum Erstellen aus der Befehlszeile "C" oder "Visual Basic" finden Sie unter [Befehlszeilenerstellung mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Füllen Sie `connectionString` die Variable im Beispiel mit den Werten für Ihre Northwind SQL Server-Beispieldatenbankverbindung. Die Windows-Authentifizierung, auch integrierte Sicherheit genannt, ist eine sicherere Möglichkeit, eine Verbindung mit der Datenbank herzustellen, als ein Kennwort in der Verbindungszeichenfolge zu speichern. Weitere Informationen zur Verbindungssicherheit finden Sie unter Schützen von [Verbindungsinformationen](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten im Windows Forms DataGridView-Steuerelement](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Schutz von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md)
