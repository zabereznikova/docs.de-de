---
title: "Gewusst wie: Hinzuf&#252;gen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenblätter, Hinzufügen von QuickInfos"
  - "DataGridView-Steuerelement [Windows Forms], Hinzufügen von QuickInfos"
  - "QuickInfo [Windows Forms], Hinzufügen zu Datenblättern"
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms
Standardmäßig werden QuickInfos verwendet, um die Werte von <xref:System.Windows.Forms.DataGridView>\-Zellen anzuzeigen, die zu klein sind, um den gesamten Inhalt anzuzeigen.  Sie können dieses Verhalten jedoch überschreiben, um QuickInfo\-Textwerte für einzelne Zellen festzulegen.  Dies bietet sich an, um Benutzern zusätzliche Informationen über eine Zelle anzuzeigen oder ihnen eine alternative Beschreibung des Zelleninhalts bereitzustellen.  Wenn Sie beispielsweise über eine Zeile verfügen, in der Zustandssymbole angezeigt werden, möchten Sie möglicherweise Texterläuterungen in Form von QuickInfos bereitstellen.  
  
 Sie können die Anzeige von QuickInfos auf Zellenebene auch deaktivieren, indem Sie die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName>\-Eigenschaft auf `false` festlegen.  
  
### So fügen Sie einer Zelle eine QuickInfo hinzu  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>\-Eigenschaft fest.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## Kompilieren des Codes  
  
-   Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `Rating` enthält, um Zeichenfolgenwerte in Form von einem bis vier Sternchensymbolen \("\*"\) anzuzeigen.  Das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis des Steuerelements muss mit der im Beispiel gezeigten Ereignishandlermethode verknüpft sein.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Robuste Programmierung  
 Wenn Sie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine externe Datenquelle binden oder Ihre eigene Datenquelle bereitstellen, indem Sie den virtuellen Modus implementieren, treten möglicherweise Leistungsprobleme auf.  Um Leistungseinbußen bei der Arbeit mit großen Datenmengen zu vermeiden, behandeln Sie das <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>\-Ereignis, anstatt die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>\-Eigenschaft mehrerer Zellen festzulegen.  Wenn Sie dieses Ereignis behandeln, wird durch Abrufen des Werts einer <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>\-Zelleneigenschaft das Ereignis ausgelöst und der Wert der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=fullName>\-Eigenschaft wie im Ereignishandler festgelegt zurückgegeben.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>   
 [Programmieren mit Zellen, Zeilen und Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)