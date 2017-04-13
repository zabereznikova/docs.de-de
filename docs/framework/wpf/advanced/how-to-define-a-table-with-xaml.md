---
title: "Gewusst wie: Definieren einer Tabelle mit XAML | Microsoft Docs"
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
  - "Dokumente, Definieren von Tabellen mit XAML"
  - "Tabellen, Definieren mit XAML"
  - "XAML, Definieren von Tabellen"
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Definieren einer Tabelle mit XAML
Im folgenden Beispiel wird das Definieren einer <xref:System.Windows.Documents.Table> mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] veranschaulicht.  Die Beispieltabelle besteht aus vier Spalten \(dargestellt durch <xref:System.Windows.Documents.TableColumn>\-Elemente\) sowie aus mehreren Zeilen \(dargestellt durch <xref:System.Windows.Documents.TableRow>\-Elemente\) und enthält sowohl Daten als auch Titel\-, Header\- und Footerinformationen.  Die Zeilen müssen in einem <xref:System.Windows.Documents.TableRowGroup>\-Element enthalten sein.  Jede Tabellenzeile besteht aus einer oder mehreren Zellen \(dargestellt durch <xref:System.Windows.Documents.TableCell>\-Elemente\).  Der Inhalt einer Tabellenzelle muss in einem <xref:System.Windows.Documents.Block>\-Element enthalten sein; in diesem Fall werden <xref:System.Windows.Documents.Paragraph>\-Elemente verwendet.  Die Tabelle enthält außerdem einen Link \(dargestellt durch das <xref:System.Windows.Documents.Hyperlink>\-Element \) in der Footerzeile.  
  
## Beispiel  
 [!code-xml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 In der folgenden Abbildung wird veranschaulicht, wie die in diesem Beispiel definierte Tabelle gerendert wird.  
  
 ![Gerenderte Tabelle.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")