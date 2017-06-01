---
title: "Gewusst wie: Erstellen eines Benutzeroberfl&#228;chen-Standarddialogfelds unter Verwendung des Grid-Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dialogfelder, Erstellen"
  - "Grid-Steuerelement, Erstellen, Dialogfeld"
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Erstellen eines Benutzeroberfl&#228;chen-Standarddialogfelds unter Verwendung des Grid-Elements
In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Standarddialogfeld mithilfe des <xref:System.Windows.Controls.Grid>\-Elements erstellt wird.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Dialogfeld erstellt, das dem Dialogfeld **Ausführen** im [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Betriebssystem ähnlich ist.  
  
 In diesem Beispiel wird ein <xref:System.Windows.Controls.Grid> erstellt. Dabei werden die Klassen <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> verwendet, um fünf Spalten und vier Zeilen zu definieren.  
  
 Anschließend wird ein <xref:System.Windows.Controls.Image>, `RunIcon.png`, hinzugefügt und positioniert, um das Bild im Dialogfeld darzustellen.  Das Bild wird in der ersten Zeile der ersten Spalte des <xref:System.Windows.Controls.Grid>\-Elements \(linke, obere Ecke\) platziert.  
  
 Dann wird der ersten Spalte ein <xref:System.Windows.Controls.TextBlock>\-Element hinzugefügt, das sich über die verbleibenden Spalten der ersten Zeile erstreckt.  Der zweiten Zeile in der ersten Spalte wird ein weiteres <xref:System.Windows.Controls.TextBlock>\-Element hinzugefügt, um das Textfeld **Öffnen** darzustellen.  Es folgt ein <xref:System.Windows.Controls.TextBlock>\-Element, das den Dateneingabebereich darstellt.  
  
 Abschließend werden in dem Beispiel drei <xref:System.Windows.Controls.Button>\-Elemente zur letzten Zeile hinzugefügt, die die Ereignisse **OK**, **Abbrechen** und **Durchsuchen** darstellen.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.GridUnitType>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)