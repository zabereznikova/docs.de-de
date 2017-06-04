---
title: "Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen | Microsoft Docs"
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
  - "AnalysisHintNode-Objekte"
  - "Analysieren von Freihandeingaben"
  - "Freihandeingaben, AnalysisHintNode-Objekte"
  - "Freihandeingaben, Analysieren"
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen
Ein <xref:System.Windows.Ink.AnalysisHintNode>\-Objekt stellt einen Hinweis für das <xref:System.Windows.Ink.InkAnalyzer>\-Objekt zur Verfügung, dem es angefügt wird.  Der Hinweis bezieht sich auf den durch die <xref:System.Windows.Ink.ContextNode.Location%2A>\-Eigenschaft von <xref:System.Windows.Ink.AnalysisHintNode> angegebenen Bereich und stellt dem InkAnalyzer\-Objekt zusätzlichen Kontext zur Verfügung, um die Erkennungsgenauigkeit zu erhöhen.  Das <xref:System.Windows.Ink.InkAnalyzer>\-Objekt verwendet diese Kontextinformationen bei der Analyse von Freihandeingaben, die es aus dem Hinweisbereich abruft.  
  
## Beispiel  
 Bei dem folgenden Beispiel handelt es sich um eine Anwendung, in der mehrere <xref:System.Windows.Ink.AnalysisHintNode>\-Objekte in einem Formular verwendet werden, das Freihandeingaben akzeptiert.  In der Anwendung wird die <xref:System.Windows.Ink.AnalysisHintNode.Factoid%2A>\-Eigenschaft verwendet, um Kontextinformationen für jeden Eintrag im Formular bereitzustellen.  In der Anwendung wird eine Hintergrundanalyse verwendet, um die Freihandeingaben zu analysieren. Fünf Sekunden nach der letzten Freihandeingabe durch den Benutzer werden sämtliche Freihandeingaben aus dem Formular gelöscht.  
  
 [!code-xml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]