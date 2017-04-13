---
title: "Gewusst wie: Erstellen eines Stiftes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Grafiken, Erstellen von Stiften"
  - "Pen-Objekt"
  - "Stifte, Erstellen"
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen eines Stiftes
In diesem Beispiel wird ein <xref:System.Drawing.Pen>\-Objekt erstellt.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## Robuste Programmierung  
 Nachdem die Verwendung von Objekten, die Systemressourcen beanspruchen, beendet ist, sollten Sie <xref:System.Drawing.Pen.Dispose%2A> für diese Objekte \(z. B. <xref:System.Drawing.Pen>\-Objekte\) aufrufen.  
  
## Siehe auch  
 <xref:System.Drawing.Pen>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Stifte, Linien und Rechtecke in GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)