---
title: "Schrifterkennung | Microsoft Docs"
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
  - "Handschrifterkennung"
  - "Erkennung der Handschrift"
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Schrifterkennung
In diesem Abschnitt werden die Grundlagen der Erkennung von Freihandeingaben auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Plattform erläutert.  
  
## Lösungsmöglichkeiten für die Schrifterkennung  
 Im folgenden Beispiel wird die Erkennung von Freihandeingaben mithilfe von <xref:System.Windows.Ink.InkAnalyzer> veranschaulicht.  
  
> [!NOTE]
>  Dieses Beispiel erfordert die Installation von Handschrifterkennungen auf dem System.  
  
 Erstellen Sie in Visual Studio 2005 ein neues [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungsprojekt mit dem Namen "InkRecognition".  Ersetzen Sie den Inhalt der Datei Window1.xaml durch den folgenden XAML\-Code:  In diesem Code wird die Benutzeroberfläche der Anwendung gerendert.  
  
 [!code-xml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Fügen Sie einen Verweis auf folgende WPF\-Assemblys zur Freihandeingabenanalyse hinzu: IAWinFX.dll, IACore.dll und IALoader.dll. Diese Assemblys sind gespeichert unter: \\Program Files\\Reference Assemblies\\Microsoft\\Tablet PC\\v1.7.  Ersetzen Sie den Inhalt der CodeBehind\-Datei durch folgenden Code:  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Ink.InkAnalyzer>   
 <xref:System.Windows.Ink.AnalysisStatus>   
 <xref:System.Windows.Controls.InkCanvas>