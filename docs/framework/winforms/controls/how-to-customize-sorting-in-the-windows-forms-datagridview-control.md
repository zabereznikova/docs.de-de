---
title: 'Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e35e340b786e078b5b1264d3f321ff952d52b439
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die automatische Sortierung. Je nach Ihren Anforderungen müssen Sie die Sortiervorgänge jedoch möglicherweise anpassen. Sie können beispielsweise mit der programmgesteuerten Sortierung eine alternative Benutzeroberfläche (UI) erstellen. Alternativ können Sie das <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignis behandeln oder die `Sort(IComparer)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode aufrufen, um flexibler sortieren zu können, z. B. beim Sortieren mehrerer Spalten.  
  
 In den folgenden Codebeispielen werden diese drei Ansätze der benutzerdefinierten Sortierung veranschaulicht. Weitere Informationen finden Sie unter [Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="programmatic-sorting"></a>Programmgesteuertes Sortieren  
 Im folgenden Codebeispiel wird eine programmgesteuerte Sortierung veranschaulicht, bei der die <xref:System.Windows.Forms.DataGridView.SortOrder%2A>-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>-Eigenschaft zum Festlegen der Sortierrichtung verwendet werden und die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A>-Eigenschaft verwendet wird, um das Sortiersymbol manuell festzulegen. Die `Sort(DataGridViewColumn,ListSortDirection)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode wird verwendet, um Daten nur in einer einzigen Spalte zu sortieren.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a>Benutzerdefinierte Sortierung mit dem SortCompare-Ereignis  
 Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit einem <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignishandler veranschaulicht. Die ausgewählte <xref:System.Windows.Forms.DataGridViewColumn> wird sortiert, und wenn die Spalte doppelte Werte enthält, wird die ID-Spalte verwendet, um die endgültige Reihenfolge zu bestimmen.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a>Benutzerdefinierte Sortierung mit der IComparer-Schnittstelle  
 Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit der `Sort(IComparer)`-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode veranschaulicht, bei der durch die Implementierung der <xref:System.Collections.IComparer>-Schnittstelle mehrere Spalten sortiert werden.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieser Beispiele über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)
