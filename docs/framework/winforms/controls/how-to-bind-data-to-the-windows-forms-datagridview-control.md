---
title: Binden von Daten an das DataGridView-Steuerelement
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745075"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Gewusst wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement

Das <xref:System.Windows.Forms.DataGridView>-Steuerelement unterstützt das Standardmodell für die Windows Forms-Datenbindung, sodass es an eine Vielzahl von Datenquellen gebunden werden kann. Normalerweise binden Sie an eine <xref:System.Windows.Forms.BindingSource>, die die Interaktion mit der Datenquelle verwaltet. Der <xref:System.Windows.Forms.BindingSource> kann eine beliebige Windows Forms Datenquelle sein, die Ihnen bei der Auswahl oder Änderung des Speicher Orts Ihrer Daten eine hohe Flexibilität bietet. Weitere Informationen zu Datenquellen, die das <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt, finden Sie unter [Übersicht über das DataGridView-Steuer](datagridview-control-overview-windows-forms.md)Element.  

Visual Studio bietet umfangreiche Unterstützung für die Datenbindung an das DataGridView-Steuerelement. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement mithilfe des Designers](bind-data-to-the-datagrid-using-the-designer.md).  

So verbinden Sie ein DataGridView-Steuerelement mit Daten:

1. Implementieren Sie eine Methode, um die Details zum Abrufen der Daten zu behandeln. Im folgenden Codebeispiel wird eine `GetData`-Methode implementiert, die ein <xref:System.Data.SqlClient.SqlDataAdapter>initialisiert und zum Auffüllen eines <xref:System.Data.DataTable>verwendet. Anschließend wird der <xref:System.Data.DataTable> an den <xref:System.Windows.Forms.BindingSource>gebunden. 

2. Binden Sie im <xref:System.Windows.Forms.Form.Load> Ereignishandler des Formulars das <xref:System.Windows.Forms.DataGridView> Steuerelement an die <xref:System.Windows.Forms.BindingSource>, und rufen Sie die `GetData`-Methode auf, um die Daten abzurufen.  

## <a name="example"></a>Beispiel

Dieses vollständige Codebeispiel ruft Daten aus einer Datenbank ab, um ein DataGridView-Steuerelement in einem Windows Form aufzufüllen. Das Formular enthält auch Schaltflächen zum erneuten Laden von Daten und Übermitteln von Änderungen an die Datenbank.  

Dieses Beispiel erfordert Folgendes: 

- Zugriff auf eine Beispieldatenbank für Northwind SQL Server. Weitere Informationen zum Installieren der Beispieldatenbank Northwind finden Sie unter [Get the Sample Database for ADO.NET Code Samples](../../data/adonet/sql/linq/downloading-sample-databases.md). 

- Verweise auf die Assemblys "System", "System. Windows. Forms", "System. Data" und "System. xml"  

Um dieses Beispiel zu erstellen und auszuführen, fügen Sie den Code in ein neues Windows Forms Projekt in die *Form1* -Codedatei ein. Weitere Informationen zum Erstellen von über C# die oder Visual Basic Befehlszeile finden Sie unter Erstellen von [Befehlszeilen mit "csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) " oder [Erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Füllen Sie die `connectionString` Variable im Beispiel mit den Werten für die Northwind-SQL Server Beispiel Datenbankverbindung. Die Windows-Authentifizierung (auch als integrierte Sicherheit bezeichnet) ist eine sicherere Möglichkeit zum Herstellen einer Verbindung mit der Datenbank als das Speichern eines Kennworts in der Verbindungs Zeichenfolge. Weitere Informationen zur Verbindungssicherheit finden Sie unter [Schützen von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten im Windows Forms DataGridView-Steuerelement](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Verbindungsinformationen schützen](../../data/adonet/protecting-connection-information.md)
