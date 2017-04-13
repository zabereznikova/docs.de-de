---
title: "Gewusst wie: Erkennen von Bewegungen in Anwendungen | Microsoft Docs"
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
  - "Anwendungsbewegungen, Erkennen"
  - "Bewegungen, Erkennen"
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Erkennen von Bewegungen in Anwendungen
Im folgenden Beispiel wird gezeigt, wie Freihandeingaben gelöscht werden können, wenn ein Benutzer eine <xref:System.Windows.Ink.ApplicationGesture>\-Bewegung auf einem <xref:System.Windows.Controls.InkCanvas> ausführt.  In diesem Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Controls.InkCanvas>\-Steuerelement mit der Bezeichnung `inkCanvas1` in der XAML\-Datei deklariert ist.  
  
## Beispiel  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Ink.ApplicationGesture>   
 <xref:System.Windows.Controls.InkCanvas>   
 <xref:System.Windows.Controls.InkCanvas.Gesture>