---
title: "Gewusst wie: Erstellen einer Reflektion | Microsoft Docs"
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
  - "Pinsel, Erstellen von Reflektionen"
  - "Erstellen von Reflektionen"
  - "Reflektionen, Erstellen"
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer Reflektion
In diesem Beispiel wird veranschaulicht, wie mithilfe von <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt wird.  Da mithilfe von <xref:System.Windows.Media.VisualBrush> vorhandene visuelle Objekte angezeigt werden können, können Sie diese Funktion zum Erstellen von interessanten visuellen Effekten wie Reflektionen and Vergrößerungen verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird mit <xref:System.Windows.Media.VisualBrush> eine Reflektion von <xref:System.Windows.Controls.Border> erstellt, die mehrere Elemente enthält.  In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein reflektiertes Visual&#45;Objekt](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
  
        Ein reflektiertes visuelles Objekt  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Das vollständige Beispiel mit weiteren Reflektionsbeispielen sowie Beispielen zum Vergrößern von Bildschirmbereichen finden Sie unter [Beispiel zu VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
## Siehe auch  
 <xref:System.Windows.Media.VisualBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)