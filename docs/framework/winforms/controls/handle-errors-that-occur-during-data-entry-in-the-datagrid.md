---
title: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement auftreten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 03a13957c80b0ab62afb11efc57cf31e059e5942
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745617"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten
Im folgenden Codebeispiel wird veranschaulicht, wie das <xref:System.Windows.Forms.DataGridView>-Steuerelement verwendet wird, um dem Benutzer Dateneingabefehler zu melden.  
  
 Eine ausführliche Erläuterung dieses Code Beispiels finden Sie unter Exemplarische Vorgehensweise [: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Data", "System.Windows.Forms" und "System.XML".  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
