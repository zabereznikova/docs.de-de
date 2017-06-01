---
title: "Gewusst wie: Synchrones Suchen in einem Storyboard | Microsoft Docs"
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
  - "Synchrones Suchen von Storyboards"
  - "Storyboards, Synchrones Suchen"
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Synchrones Suchen in einem Storyboard
In dem folgenden Beispiel wird veranschaulicht, wie mit der <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>\-Methode eines <xref:System.Windows.Media.Animation.Storyboard> eine beliebige Position in einer Storyboard\-Animation synchron gesucht wird.  
  
## Beispiel  
 Im Folgenden wird das XAML\-Markup für das Beispiel dargestellt.  
  
 [!code-xml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## Beispiel  
 Im Folgenden wird der Code dargestellt, der zusammen mit dem obigen XAML\-Code verwendet wird.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]