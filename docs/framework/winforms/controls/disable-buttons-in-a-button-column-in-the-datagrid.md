---
title: "Gewusst wie: Deaktivieren von Schaltfl&#228;chen in einer Schaltfl&#228;chenspalte im DataGridView-Steuerelement von Windows Forms | Microsoft Docs"
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
  - "Schaltflächen, Deaktivieren in Schaltflächenspalten"
  - "Datenblätter, Deaktiveren von Schaltflächen"
  - "DataGridView-Steuerelement [Windows Forms], Deaktivieren von Schaltflächenzellen"
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Deaktivieren von Schaltfl&#228;chen in einer Schaltfl&#228;chenspalte im DataGridView-Steuerelement von Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält die <xref:System.Windows.Forms.DataGridViewButtonCell>\-Klasse, über die Zellen mit einer schaltflächenähnlichen Benutzeroberfläche angezeigt werden können.  <xref:System.Windows.Forms.DataGridViewButtonCell> bietet jedoch keine Möglichkeit, die Darstellung der in der Zelle angezeigten Schaltfläche zu deaktivieren.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.DataGridViewButtonCell>\-Klasse angepasst wird, um Schaltflächen anzuzeigen, die deaktiviert angezeigt werden können.  Im Beispiel wird der neue Zellentyp `DataGridViewDisableButtonCell` definiert, der aus <xref:System.Windows.Forms.DataGridViewButtonCell> abgeleitet wird.  Dieser Zellentyp stellt eine neue `Enabled`\-Eigenschaft bereit, die auf `false` festgelegt werden kann, um eine deaktivierte Schaltfläche in der Zelle zu zeichnen.  Im Beispiel wird auch der neue Spaltentyp `DataGridViewDisableButtonColumn` definiert, der `DataGridViewDisableButtonCell`\-Objekte anzeigt.  Zur Veranschaulichung dieses neuen Zellen\- und Spaltentyps wird durch den aktuellen Wert jeder <xref:System.Windows.Forms.DataGridViewCheckBoxCell> im übergeordneten <xref:System.Windows.Forms.DataGridView> bestimmt, ob die `Enabled`\-Eigenschaft der `DataGridViewDisableButtonCell` in derselben Zeile gleich `true` oder gleich `false` ist.  
  
> [!NOTE]
>  Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`\-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden.  Außerdem sollten Sie die `Clone`\-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing", "System.Windows.Forms" und "System.Windows.Forms.VisualStyles".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Architektur des DataGridView\-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)