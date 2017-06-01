---
title: "Gewusst wie: Erstellen eines Pinsels in Volltonfarbe | Microsoft Docs"
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
  - "Pinsel, Erstellen von Vollton"
  - "Pinsel, Beispiele"
  - "Volltonfarbpinsel"
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines Pinsels in Volltonfarbe
Dieses Beispiel erstellt ein <xref:System.Drawing.SolidBrush>\-Objekt, das von einem <xref:System.Drawing.Graphics>\-Objekt zum Ausfüllen von Formen verwendet werden kann.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## Robuste Programmierung  
 Nach der Verwendung von Objekten, die Systemressourcen verbrauchen \(z. B. Brush\-Objekte\), sollten Sie für diese Objekte <xref:System.IDisposable.Dispose%2A> aufrufen.  
  
## Siehe auch  
 <xref:System.Drawing.SolidBrush>   
 <xref:System.Drawing.Brush>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Pinsel und gefüllte Formen in GDI\+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)   
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)