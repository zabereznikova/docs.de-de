---
title: Validieren von Daten im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 5fd881829f87fa1dec135d936f22996f196b0594
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728305"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Überprüfen von Daten im DataGridView-Steuerelement in Windows Forms
Im folgenden Codebeispiel wird gezeigt, wie Daten validiert werden, die von einem Benutzer in ein <xref:System.Windows.Forms.DataGridView>-Steuerelement eingegeben wurden. In diesem Beispiel wird die <xref:System.Windows.Forms.DataGridView> mit Zeilen aus der Tabelle `Customers` der Northwind-Beispieldatenbank gefüllt. Wenn der Benutzer eine Zelle in der Spalte `CompanyName` bearbeitet, wird der Wert auf Gültigkeit überprüft, indem geprüft wird, dass die Zelle nicht leer ist. Wenn der Ereignishandler für das <xref:System.Windows.Forms.DataGridView.CellValidating>-Ereignis feststellt, dass es sich bei dem Wert um eine leere Zeichenfolge handelt, sorgt die <xref:System.Windows.Forms.DataGridView> dafür, dass der Benutzer die Zelle erst verlassen kann, nachdem er eine nicht leere Zeichenfolge eingegeben hat.  
  
 Eine vollständige Erläuterung dieses Codebeispiels finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Data", "System.Windows.Forms" und "System.XML".  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
