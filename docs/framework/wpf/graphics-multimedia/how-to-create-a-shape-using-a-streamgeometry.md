---
title: "Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry | Microsoft Docs"
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
  - "Klassen, StreamGeometry"
  - "Grafiken [WPF], Formen"
  - "Formen, Erstellen mit StreamGeometry-Klasse"
  - "StreamGeometry-Klasse"
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry
<xref:System.Windows.Media.StreamGeometry> ist eine einfache Alternative zu <xref:System.Windows.Media.PathGeometry> zum Erstellen geometrischer Formen.  Verwenden Sie <xref:System.Windows.Media.StreamGeometry>, wenn Sie eine komplexe Geometrie beschreiben müssen, aber ohne den Verwaltungsaufwand zur Unterstützung von Datenbindung, Animation oder Änderungen auskommen möchten.  Aufgrund ihrer Effizienz ist z. B. die <xref:System.Windows.Media.StreamGeometry>\-Klasse eine gute Wahl zum Beschreiben von Adornern.  
  
## Beispiel  
 Im folgenden Beispiel wird mithilfe der Attributsyntax eine dreieckige <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt.  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.StreamGeometry>\-Attributsyntax finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
## Beispiel  
 Im nächsten Beispiel wird <xref:System.Windows.Media.StreamGeometry> verwendet, um ein Dreieck in Code zu definieren.  Im Beispiel wird zuerst eine <xref:System.Windows.Media.StreamGeometry> erstellt, dann ein <xref:System.Windows.Media.StreamGeometryContext> abgerufen und zur Beschreibung des Dreiecks verwendet.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## Beispiel  
 Im nächsten Beispiel wird eine Methode erstellt, die mithilfe von <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.StreamGeometryContext> anhand der angegebenen Parameter eine geometrische Form definiert.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.StreamGeometryContext>   
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)