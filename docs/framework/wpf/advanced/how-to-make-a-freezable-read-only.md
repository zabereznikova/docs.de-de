---
title: "Gewusst wie: Erstellen eines schreibgesch&#252;tzten Freezable-Objekts | Microsoft Docs"
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
  - "Freezable-Objekte, Als schreibgeschützt markieren"
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen eines schreibgesch&#252;tzten Freezable-Objekts
In diesem Beispiel wird dargestellt, wie der Schreibschutz für ein <xref:System.Windows.Freezable> mithilfe des Aufrufs der <xref:System.Windows.Freezable.Freeze%2A>\-Methode aktiviert wird.  
  
 Ein <xref:System.Windows.Freezable>\-Objekt kann nicht fixiert werden, wenn eine der folgenden Bedingungen in Bezug auf das Objekt `true` ist:  
  
-   Es verfügt über animierte oder datengebundene Eigenschaften.  
  
-   Es verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden.  Weitere Informationen zu dynamischen Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Es enthält untergeordnete <xref:System.Windows.Freezable>\-Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen `false` in Bezug auf das <xref:System.Windows.Freezable>\-Objekt sind und keine Änderungen nötig sind, sollten Sie zur Leistungsverbesserung das Fixieren des Objekts in Betracht ziehen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> fixiert, der vom Typ <xref:System.Windows.Freezable>\-Objekt ist.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Weitere Informationen über <xref:System.Windows.Freezable>\-Objekte finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CanFreeze%2A>   
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)