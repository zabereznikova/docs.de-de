---
title: Binden von Daten an das DataGridView-Steuerelement
ms.date: 02/08/2019
description: Erfahren Sie, wie das DataGridView-Steuerelement das Standard Windows Forms-Daten Bindungs Modell unterstützt, sodass es an eine Vielzahl von Datenquellen gebunden werden kann.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904415"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Gewusst wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement

Das- <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt das Standard-Daten Bindungs Modell Windows Forms, sodass es an eine Vielzahl von Datenquellen gebunden werden kann. Normalerweise binden Sie an einen <xref:System.Windows.Forms.BindingSource> , der die Interaktion mit der Datenquelle verwaltet. Der <xref:System.Windows.Forms.BindingSource> kann eine beliebige Windows Forms Datenquelle sein, die Ihnen bei der Auswahl oder Änderung des Speicher Orts Ihrer Daten eine hohe Flexibilität bietet. Weitere Informationen zu den vom-Steuerelement unterstützten Datenquellen finden Sie unter <xref:System.Windows.Forms.DataGridView> [Übersicht über das DataGridView-Steuer](datagridview-control-overview-windows-forms.md)Element.  

Visual Studio bietet umfangreiche Unterstützung für die Datenbindung an das DataGridView-Steuerelement. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an das Windows Forms DataGridView-Steuerelement mithilfe des Designers](bind-data-to-the-datagrid-using-the-designer.md).  

So verbinden Sie ein DataGridView-Steuerelement mit Daten:

1. Implementieren Sie eine Methode, um die Details zum Abrufen der Daten zu behandeln. Im folgenden Codebeispiel wird eine `GetData` Methode implementiert, die eine initialisiert <xref:System.Data.SqlClient.SqlDataAdapter> und diese zum Auffüllen einer verwendet <xref:System.Data.DataTable> . Anschließend wird der <xref:System.Data.DataTable> an die gebunden <xref:System.Windows.Forms.BindingSource> .

2. Binden Sie im- <xref:System.Windows.Forms.Form.Load> Ereignishandler des Formulars das <xref:System.Windows.Forms.DataGridView> -Steuerelement an <xref:System.Windows.Forms.BindingSource> , und rufen `GetData` Sie die-Methode auf, um die Daten abzurufen.  

## <a name="example"></a>Beispiel

Dieses vollständige Codebeispiel ruft Daten aus einer Datenbank ab, um ein DataGridView-Steuerelement in einem Windows Form aufzufüllen. Das Formular enthält auch Schaltflächen zum erneuten Laden von Daten und Übermitteln von Änderungen an die Datenbank.  

Für dieses Beispiel benötigen Sie Folgendes:

- Zugriff auf eine Beispieldatenbank für Northwind SQL Server. Weitere Informationen zum Installieren der Beispieldatenbank Northwind finden Sie unter [Get the Sample Database for ADO.NET Code Samples](../../data/adonet/sql/linq/downloading-sample-databases.md).

- Verweise auf die Assemblys "System", "System. Windows. Forms", "System. Data" und "System.Xml"  

Um dieses Beispiel zu erstellen und auszuführen, fügen Sie den Code in ein neues Windows Forms Projekt in die *Form1* -Codedatei ein. Weitere Informationen zum Erstellen aus der c#-oder Visual Basic-Befehlszeile finden Sie unter Erstellen von [Befehlszeilen mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Füllen Sie die `connectionString` Variable im Beispiel mit den Werten für Ihre Northwind-SQL Server-Beispiel Datenbankverbindung auf. Die Windows-Authentifizierung (auch als integrierte Sicherheit bezeichnet) ist eine sicherere Möglichkeit zum Herstellen einer Verbindung mit der Datenbank als das Speichern eines Kennworts in der Verbindungs Zeichenfolge. Weitere Informationen zur Verbindungssicherheit finden Sie unter [Schützen von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten im Windows Forms DataGridView-Steuerelement](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Verbindungsinformationen schützen](../../data/adonet/protecting-connection-information.md)
