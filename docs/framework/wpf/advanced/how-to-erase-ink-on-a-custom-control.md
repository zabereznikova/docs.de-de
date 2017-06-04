---
title: "Gewusst wie: L&#246;schen von Freihandeingaben auf einem benutzerdefinierten Steuerelement | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente, Löschen von Freihandeingaben in"
  - "Freihandeingaben, Löschen in benutzerdefinierten Steuerelement"
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: L&#246;schen von Freihandeingaben auf einem benutzerdefinierten Steuerelement
Durch <xref:System.Windows.Ink.IncrementalStrokeHitTester> wird ermittelt, ob sich der gerade gezogene Strich mit einem anderen Strich überschneidet.  Dadurch kann ein Steuerelement erstellt werden, mit dem Benutzer Teile eines Strichs auf die gleiche Art und Weise löschen können, wie bei einem <xref:System.Windows.Controls.InkCanvas>\-Steuerelement, wenn für <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> die Einstellung <xref:System.Windows.Controls.InkCanvasEditingMode> festgelegt ist.  
  
## Beispiel  
 Im folgenden Beispiel wird ein benutzerdefiniertes Steuerelement erstellt, mit dem Benutzer Teile von Strichen löschen können.  In diesem Beispiel wird ein Steuerelement erstellt, das bei seiner Initialisierung Freihandeingaben enthält.  Informationen zum Erstellen eines Steuerelements, das Freihandeingaben erfasst, finden Sie unter [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]