---
title: "Gewusst wie: Drehen von Freihandeingaben | Microsoft Docs"
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
  - "Freihandeingaben, Drehen"
  - "Drehen von Freihandeingaben"
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Drehen von Freihandeingaben
## Beispiel  
 In folgendem Beispiel wird die Freihandeingabe eines <xref:System.Windows.Controls.InkCanvas> auf einen <xref:System.Windows.Controls.Canvas> kopiert, der einen <xref:System.Windows.Controls.InkPresenter> enthält.  Wenn die Anwendung die Freihandeingabe kopiert, wird diese gleichzeitig um 90 Grad im Uhrzeigersinn gedreht.  
  
 [!code-xml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## Beispiel  
 Das folgende Beispiel ist ein benutzerdefinierter <xref:System.Windows.Documents.Adorner>, der die Striche in einem <xref:System.Windows.Controls.InkPresenter> dreht.  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 Das folgende Beispiel ist eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei, die einen <xref:System.Windows.Controls.InkPresenter> definiert und mit Freihandeingaben füllt.  Der `Window_Loaded`\-Ereignishandler fügt dem <xref:System.Windows.Controls.InkPresenter> den benutzerdefinierten Adorner hinzu.  
  
 [!code-xml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]