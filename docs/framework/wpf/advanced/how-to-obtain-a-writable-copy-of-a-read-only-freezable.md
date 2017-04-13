---
title: "Gewusst wie: Erstellen einer &#252;berschreibbaren Kopie eines schreibgesch&#252;tzten Freezable-Objekts | Microsoft Docs"
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
  - "Klonen von Freezable-Objekten"
  - "Freezable-Objekte, Änderbare Klone"
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen einer &#252;berschreibbaren Kopie eines schreibgesch&#252;tzten Freezable-Objekts
In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Windows.Freezable.Clone%2A>\-Methode eine überschreibbare Kopie eines schreibgeschützten <xref:System.Windows.Freezable> erstellt werden kann.  
  
 Nachdem ein <xref:System.Windows.Freezable>\-Objekt als schreibgeschützt \("fixiert"\) markiert wurde, kann es nicht geändert werden.  Sie können jedoch mithilfe der <xref:System.Windows.Freezable.Clone%2A>\-Methode einen änderbaren Klon des fixierten Objekts erstellen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein änderbarer Klon eines fixierten <xref:System.Windows.Media.SolidColorBrush>\-Objekts erstellt.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Weitere Informationen über <xref:System.Windows.Freezable>\-Objekte finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)