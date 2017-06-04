---
title: "Gewusst wie: Auflisten von Systemschriftarten | Microsoft Docs"
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
  - "Auflisten, Systemschriftarten"
  - "Schriftarten, Auflisten"
  - "Systemschriftarten, Auflisten"
  - "Typografie, Auflisten von Systemschriftarten"
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Auflisten von Systemschriftarten
## Beispiel  
 Im folgenden Beispiel wird verdeutlicht, wie die Schriftarten in der Auflistung der Systemschriftarten aufgelistet werden.  Der Name der Schriftfamilie jeder <xref:System.Windows.Media.FontFamily> innerhalb von <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> wird einem Kombinationsfeld als Element hinzugefügt.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Wenn sich mehrere Versionen derselben Schriftfamilie im selben Verzeichnis befinden, gibt die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Schriftartauflistung die aktuellste Version der Schriftart zurück.  Wenn die Versionsinformationen keinen Aufschluss geben, wird die Schriftart mit dem aktuellsten Timestamp zurückgegeben.  Wenn die Timestampinformationen gleich sind, wird die Schriftartdatei zurückgegeben, die sich in der alphabetischen Reihenfolge an erster Position befindet.