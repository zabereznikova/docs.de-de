---
title: "Speichern von Freihandeingaben | Microsoft Docs"
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
  - "Ink Serialized Format (ISF)"
  - "Freihandeingaben, Speichern"
  - "ISF (Ink Serialized Format)"
  - "Abrufen von Eingabehilfen"
  - "Speichern von Eingabehilfen"
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Speichern von Freihandeingaben
Von den <xref:System.Windows.Ink.StrokeCollection.Save%2A>\-Methoden wird das Speichern von Freihandeingaben als ISF \(Ink Serialized Format\) unterstützt.  Von den Konstruktoren für die <xref:System.Windows.Ink.StrokeCollection>\-Klasse wird das Lesen von Freihanddaten unterstützt.  
  
## Speichern und Abrufen von Freihandeingaben  
 In diesem Abschnitt wird das Speichern und Abrufen von Freihandeingaben auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Plattform erläutert.  
  
 Im folgenden Beispiel wird ein Schaltflächenklick\-Ereignishandler implementiert, von dem ein Datei speichern\-Dialogfeld bereitgestellt und die Freihandeingabe von einem <xref:System.Windows.Controls.InkCanvas>\-Steuerelement in einer Datei gespeichert wird.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 Im folgenden Beispiel wird ein Schaltflächenklick\-Ereignishandler implementiert, von dem ein Datei öffnen\-Dialogfeld bereitgestellt und die Freihandeingabe aus der Datei in ein <xref:System.Windows.Controls.InkCanvas>\-Element eingelesen wird.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.InkCanvas>   
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)