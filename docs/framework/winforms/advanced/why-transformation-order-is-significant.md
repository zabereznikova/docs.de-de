---
title: "Bedeutung der Transformationsreihenfolge | Microsoft Docs"
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
  - "Transformationen, Reihenfolge"
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Bedeutung der Transformationsreihenfolge
In einem einzelnen <xref:System.Drawing.Drawing2D.Matrix>\-Objekt kann entweder eine einzelne Transformation oder eine Abfolge von Transformationen gespeichert werden.  Der zweite Vorgang wird als zusammengesetzte Transformation bezeichnet.  Die Matrix einer zusammengesetzten Transformation ergibt sich aus der Multiplikation der Matrizen der einzelnen Transformationen.  
  
## Beispiele für zusammengesetzte Transformationen  
 In einer zusammengesetzten Transformation ist die Reihenfolge der einzelnen Transformationen von Bedeutung.  Wenn Sie beispielsweise zuerst eine Drehung, dann eine Skalierung und zuletzt eine Verschiebung durchführen, erhalten Sie ein anderes Ergebnis, als wenn Sie zuerst eine Verschiebung, dann eine Drehung und zuletzt eine Skalierung durchführen.  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sind zusammengesetzte Transformationen von links nach rechts aufgebaut.  Wenn S, D und Ü der Skalierungs\-, Drehungs\- und Verschiebungsmatrix entsprechen, dann ist das Produkt SDÜ \(in dieser Reihenfolge\) die Matrix der zusammengesetzten Transformation, bei der zunächst die Skalierung, dann die Drehung und zuletzt die Verschiebung erfolgt.  Die Matrix, die das Ergebnis des Produkts SDÜ ist, unterscheidet sich von der Matrix, die das Ergebnis des Produkts ÜDS ist.  
  
 Ein Grund, warum die Reihenfolge von Transformationen, wie Drehungen und Skalierungen, wichtig ist, liegt darin, dass sie mit Bezug auf den Ursprung des Koordinatensystems durchgeführt werden.  Die Skalierung eines Objekts, dessen Mittelpunkt im Ursprung liegt, ergibt ein anderes Ergebnis als die Skalierung eines Objekts, das vom Ursprung verschoben wurde.  Analog dazu ergibt die Drehung eines Objekts, dessen Mittelpunkt im Ursprung liegt, ein anderes Ergebnis als die Drehung eines Objekts, das vom Ursprung verschoben wurde.  
  
 Im folgenden Beispiel bildet die Aneinanderreihung von Skalierung, Drehung und Verschiebung \(in dieser Reihenfolge\) eine zusammengesetzte Transformation.  Das Argument <xref:System.Drawing.Drawing2D.MatrixOrder>, das an die <xref:System.Drawing.Graphics.RotateTransform%2A>\-Methode übergeben wird, zeigt an, dass die Drehung im Anschluss an die Skalierung erfolgt.  Dementsprechend zeigt das Argument <xref:System.Drawing.Drawing2D.MatrixOrder>, das an die <xref:System.Drawing.Graphics.TranslateTransform%2A>\-Methode übergeben wird, an, dass die Verschiebung im Anschluss an die Drehung erfolgt.  <xref:System.Drawing.Drawing2D.MatrixOrder> und <xref:System.Drawing.Drawing2D.MatrixOrder> sind Member der <xref:System.Drawing.Drawing2D.MatrixOrder>\-Enumeration.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 Im folgenden Beispiel werden die gleichen Methoden wie im vorherigen Beispiel aufgerufen, allerdings in umgekehrter Reihenfolge.  Daraus ergibt sich die folgende Reihenfolge der Operationen: erst Verschiebung, dann Drehung und dann Skalierung. Das auf diese Weise produzierte Ergebnis unterscheidet sich erheblich von der Reihenfolge Skalierung, dann Drehung, dann Verschiebung.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Eine Möglichkeit, die Reihenfolge der einzelnen Transformationen in einer zusammengesetzten Transformation umzukehren, besteht darin, die Reihenfolge der aufeinander folgenden Methodenaufrufe umzukehren.  Eine zweite Möglichkeit, die Operationsreihenfolge zu steuern, besteht darin, das Argument für die Matrixreihenfolge zu ändern.  Das folgende Beispiel ist mit dem vorangehenden Beispiel identisch, abgesehen davon, dass <xref:System.Drawing.Drawing2D.MatrixOrder> in <xref:System.Drawing.Drawing2D.MatrixOrder> geändert wurde.  Die Matrixmultiplikation erfolgt in der Reihenfolge SDV, wobei S, D und V jeweils den Matrizen für Skalierung, Drehung und Verschiebung entsprechen.  Die Reihenfolge der zusammengesetzten Transformation lautet: zuerst Skalierung, dann Drehung, dann Verschiebung.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Das Ergebnis des unmittelbar vorangehenden Beispiels ist identisch mit dem Ergebnis des ersten Beispiels in diesem Thema.  Das liegt daran, dass sowohl die Reihenfolge der Methodenaufrufe als auch die Reihenfolge der Matrixmultiplikation umgekehrt wurde.  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Verwenden von Transformationen in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)