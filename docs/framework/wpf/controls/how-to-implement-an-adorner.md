---
title: "Gewusst wie: Implementieren eines Adorners | Microsoft Docs"
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
  - "Adorner, Implementieren"
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Implementieren eines Adorners
In diesem Beispiel wird die minimale Implementierung eines Adorners erläutert.  
  
## Hinweise für Implementierer  
 Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Sicherzustellen, dass ein Adorner rendert, ist Aufgabe des Implementierers.  Zur Implementierung von Renderingverhalten wird meistens die <xref:System.Windows.UIElement.OnRender%2A>\-Methode überschrieben, und es werden ein oder mehrere <xref:System.Windows.Media.DrawingContext>\-Objekte verwendet, um die Darstellung des Adorners wie gewünscht zu rendern \(wie in diesem Beispiel gezeigt\).  
  
## Beispiel  
  
### Beschreibung  
 Ein benutzerdefinierter Adorner wird erstellt, indem man eine Klasse implementiert, die von der abstrakten <xref:System.Windows.Documents.Adorner>\-Klasse erbt.  Der Beispieladorner versieht einfach die Ecken eines <xref:System.Windows.UIElement> mit Kreisen, indem er die <xref:System.Windows.UIElement.OnRender%2A>\-Methode überschreibt.  
  
### Code  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)