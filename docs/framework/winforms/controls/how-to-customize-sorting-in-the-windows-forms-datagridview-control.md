---
title: "Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenblätter, Anpassen des Sortierens"
  - "DataGridView-Steuerelement [Windows Forms], Sortieren"
  - "Sortieren, DataGridView-Steuerelement"
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ermöglicht die automatische Sortierung. Je nach Ihren Anforderungen müssen Sie die Sortiervorgänge jedoch möglicherweise anpassen.  Sie können beispielsweise mit der programmgesteuerten Sortierung eine alternative Benutzeroberfläche \(UI\) erstellen.  Alternativ können Sie das <xref:System.Windows.Forms.DataGridView.SortCompare>\-Ereignis behandeln oder die `Sort(IComparer)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode aufrufen, um flexibler sortieren zu können, z. B. beim Sortieren mehrerer Spalten.  
  
 In den folgenden Codebeispielen werden diese drei Ansätze der benutzerdefinierten Sortierung veranschaulicht.  Weitere Informationen finden Sie unter [Spaltenssortiermodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## Programmgesteuertes Sortieren  
 Im folgenden Codebeispiel wird eine programmgesteuerte Sortierung veranschaulicht, bei der die <xref:System.Windows.Forms.DataGridView.SortOrder%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>\-Eigenschaft zum Festlegen der Sortierrichtung verwendet werden und die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A>\-Eigenschaft verwendet wird, um das Sortiersymbol manuell festzulegen.  Die `Sort(DataGridViewColumn,ListSortDirection)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode wird verwendet, um Daten nur in einer einzigen Spalte zu sortieren.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## Benutzerdefinierte Sortierung mit dem SortCompare\-Ereignis  
 Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit einem <xref:System.Windows.Forms.DataGridView.SortCompare>\-Ereignishandler veranschaulicht.  Die ausgewählte <xref:System.Windows.Forms.DataGridViewColumn> wird sortiert, und wenn die Spalte doppelte Werte enthält, wird die ID\-Spalte verwendet, um die endgültige Reihenfolge zu bestimmen.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## Benutzerdefinierte Sortierung mit der IComparer\-Schnittstelle  
 Im folgenden Codebeispiel wird eine benutzerdefinierte Sortierung mit der `Sort(IComparer)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode veranschaulicht, bei der durch die Implementierung der <xref:System.Collections.IComparer>\-Schnittstelle mehrere Spalten sortiert werden.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieser Beispiele über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Sortieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Spaltenssortiermodi im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)