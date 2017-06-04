---
title: "Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Farbverläufe, Systemfarben in"
  - "Systemfarben in Farbverläufen"
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf
Zur Verwendung von Systemfarben in einem Farbverlauf erzeugen Sie mithilfe der statischen *\<SystemColor\>*Color\- und *\<SystemColor\>*ColorKey\-Eigenschaften der <xref:System.Windows.SystemColors>\-Klasse einen Verweis auf die Farbe, wobei *\<SystemColor\>* den Namen der gewünschten Systemfarbe darstellt.  Verwenden Sie die *\<SystemColor\>*ColorKey\-Eigenschaften, um einen dynamischen Verweis zu erstellen, der bei einer Änderung des Systemdesigns automatisch aktualisiert wird.  Verwenden Sie andernfalls die *\<SystemColor\>*Color\-Eigenschaften.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.SystemColors>   
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)