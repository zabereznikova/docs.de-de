---
title: "Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Zellen, Textausrichtung"
  - "Währungsangaben, Formatieren in Datenblättern"
  - "Daten [Windows Forms], Formatieren im DataGridView-Steuerelement"
  - "Datenblätter, Währungsangaben"
  - "Datenblätter, Datumswerte"
  - "Datenblätter, Aktivieren des Zeilenumbruchs"
  - "Datenblätter, Formatieren von Daten"
  - "Datenblätter, Textausrichtung"
  - "DataGridView-Steuerelement [Windows Forms], Formatieren von Daten"
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms
In den folgenden Prozeduren wird die grundlegende Formatierung von Zellenwerten mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>\-Eigenschaft eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements sowie von bestimmten Spalten in einem Steuerelement veranschaulicht.  Weitere Informationen über die erweiterte Datenformatierung finden Sie unter [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### So formatieren Sie Währungs\- und Datumswerte  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>\-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> fest.  Im folgenden Codebeispiel wird das Format für bestimmte Spalten mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>\-Eigenschaft der Spalten festgelegt.  Werte in der Spalte  `UnitPrice`  werden im aktuellen kulturspezifischen Währungsformat angezeigt, wobei negative Werte in Klammern eingeschlossen sind.  Werte in der Spalte  `ShipDate`  werden im aktuellen kulturspezifischen kurzen Datumsformat angezeigt.  Weitere Informationen zu <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>\-Werten finden Sie unter [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### So passen Sie die Anzeige von NULL\-Datenbankwerten an  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>\-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> fest.  Das folgende Codebeispiel verwendet die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft, um in allen Zellen mit Werten gleich <xref:System.DBNull.Value?displayProperty=fullName> "no entry" anzuzeigen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### So aktivieren Sie den Zeilenumbruch in textbasierten Zellen  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>\-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewTriState>\-Enumerationswerte fest.  Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft verwendet, um den Umbruchmodus für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### So geben Sie die Textausrichtung von DataGridView\-Zellen an  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>\-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewCellStyle> auf einen der <xref:System.Windows.Forms.DataGridViewContentAlignment>\-Enumerationswerte fest.  Im folgenden Codebeispiel wird die Ausrichtung für eine bestimmte Spalte mithilfe der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>\-Eigenschaft der Spalte festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## Kompilieren des Codes  
 Für diese Beispiele gelten folgende Voraussetzungen:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte mit dem Namen `UnitPrice`, eine Spalte mit dem Namen `ShipDate` und eine Spalte mit dem Namen `CustomerName` enthält.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Robuste Programmierung  
 Um maximale Skalierbarkeit zu erreichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte für mehrere Zeilen, Spalten oder Zellen, die dieselben Stile verwenden, freigeben, anstatt die Stileigenschaften für einzelne Elemente separat festzulegen.  Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Formatierung von Typen](../../../../docs/standard/base-types/formatting-types.md)