---
title: "Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Anpassen von Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Anpassen von Zeilen"
  - "Zeilen, Anpassen im DataGridView-Steuerelement"
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms
Sie können die Darstellung von <xref:System.Windows.Forms.DataGridView>\-Zeilen steuern, indem Sie eines oder beide der Ereignisse <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName> und <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName> behandeln.  Diese Ereignisse sind so konzipiert, dass Sie nur das Gewünschte zeichnen und das <xref:System.Windows.Forms.DataGridView>\-Steuerelement den Rest zeichnen lassen.  Wenn Sie beispielsweise einen benutzerdefinierten Hintergrund zeichnen möchten, können Sie das <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>\-Ereignis behandeln und dafür sorgen, dass einzelne Zellen ihren eigenen Vordergrundinhalt zeichnen.  Alternativ können Sie dafür sorgen, dass sich die Zellen selbst zeichnen und in einem Handler des <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>\-Ereignisses benutzerdefinierte Vordergrundinhalte hinzufügen.  Sie können auch das Zeichnen von Zellen deaktivieren und in einem <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>\-Ereignishandler alles selbst zeichnen.  
  
 Im folgende Codebeispiel werden Handler für beide Ereignisse implementiert, um einen Hintergrund mit einer Farbverlaufsauswahl und einige benutzerdefinierte Vordergrundinhalte bereitzustellen, die über mehrere Spalten gehen.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Architektur des DataGridView\-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)