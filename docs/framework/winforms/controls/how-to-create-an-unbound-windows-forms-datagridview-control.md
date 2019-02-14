---
title: 'Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: f4f36622d16ee7b1fcbd743f73e376283d04e76a
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261049"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements
Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement programmgesteuert mit Daten aufgefüllt wird, ohne dass das Element an eine Datenquelle gebunden wird. Dies ist hilfreich, wenn Sie über eine kleine Menge Daten verfügen, die Sie in einem Tabellenformat anzeigen möchten.  
  
 Eine vollständige Erläuterung dieses Codebeispiels, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  

## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- [Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
