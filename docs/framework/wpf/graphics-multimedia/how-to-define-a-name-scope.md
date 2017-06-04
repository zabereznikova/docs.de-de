---
title: "Gewusst wie: Definieren eines Namensbereichs | Microsoft Docs"
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
  - "Animation, Storyboards, In prozeduralem Code"
  - "Namensbereich, Definieren"
  - "Storyboards, Animieren in prozeduralem Code"
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Definieren eines Namensbereichs
Um mit dem <xref:System.Windows.Media.Animation.Storyboard> im Code zu animieren, müssen Sie einen <xref:System.Windows.NameScope> erstellen und die Namen der Zielobjekte bei dem Element registrieren, das Besitzer des Namensbereichs ist.  Im folgenden Beispiel wird ein <xref:System.Windows.NameScope> für `myMainPanel` erstellt.  Dem Bereich werden zwei Schaltflächen, `button1` und `button2` hinzugefügt, und ihre Namen werden registriert.  Mehrere Animationen und ein <xref:System.Windows.Media.Animation.Storyboard> werden erstellt.  Die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode des Storyboards wird verwendet, um die Animationen zu starten.  
  
 Da `button1`, `button2` und `myMainPanel` alle denselben Namensbereich gemeinsam nutzen, kann jedes dieser Elemente mit der <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode verwendet werden, um die Animationen zu starten.  
  
## Beispiel  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)