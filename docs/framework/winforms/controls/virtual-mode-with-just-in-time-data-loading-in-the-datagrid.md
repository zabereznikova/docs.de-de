---
title: 'Gewusst wie: Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: c5b218786d2b52037ec9009ac9fd68c089b1bb47
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732435"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms
Im folgenden Codebeispiel wird gezeigt, wie der virtuelle Modus im <xref:System.Windows.Forms.DataGridView>-Steuerelement mit einem Datencache verwendet wird, der nur bei Bedarf die Daten von einem Server lädt. In diesem Beispiel wird ausführlich beschrieben [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys System, System.Data, System.XML und System.Windows.Forms.  
  
-   Zugriff auf einen Server mit der SQL Server-Beispieldatenbank Northwind.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
