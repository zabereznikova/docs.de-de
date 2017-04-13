---
title: "Gewusst wie: Treffer&#252;berpr&#252;fung mit einem Bereich | Microsoft Docs"
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
  - "Treffertests, Verwenden von Bereichen"
  - "Bereiche, Treffertests"
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Treffer&#252;berpr&#252;fung mit einem Bereich
Der Zweck der Trefferüberprüfung besteht darin zu ermitteln, ob sich der Cursor über einem bestimmten Objekt, z. B. einem Symbol oder einer Schaltfläche, befindet.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Bereich in Form eines Pluszeichens gebildet, indem zwei rechteckige Bereiche zusammengeführt werden.  Es wird davon ausgegangen, dass in der Variablen  `point`  der Punkt angegeben ist, an dem zuletzt geklickt wurde.  Anhand des Codes wird überprüft, ob sich  `point`  in dem Bereich befindet, der das Pluszeichen bildet.  Befindet sich `point` in diesem Bereich \(ein Treffer\), wird der Bereich mit einer deckenden roten Pinselfarbe gefüllt.  Andernfalls wird der Bereich mit einer halb transparenten Pinselfarbe gefüllt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 <xref:System.Drawing.Region>   
 [Bereiche in GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Gewusst wie: Ausschneiden mit einem Bereich](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)