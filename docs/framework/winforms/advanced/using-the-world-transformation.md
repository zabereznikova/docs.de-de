---
title: "Verwenden der globalen Transformation | Microsoft Docs"
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
  - "Grafiken, Globale Transformation"
  - "Globale Transformation, Beispiele"
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Verwenden der globalen Transformation
Die globale Transformation ist eine Eigenschaft der <xref:System.Drawing.Graphics>\-Klasse.  Die Zahlen, die die globale Transformation angeben, sind in einem <xref:System.Drawing.Drawing2D.Matrix>\-Objekt gespeichert, das eine 3x3\-Matrix darstellt.  Die <xref:System.Drawing.Drawing2D.Matrix>\-Klasse und die <xref:System.Drawing.Graphics>\-Klasse verfügen über mehrere Methoden zum Festlegen der Zahlen in der globalen Transformationsmatrix.  
  
## Andere Typen von Transformationen  
 Im folgenden Beispiel wird durch den Code zunächst ein 50x50\-Rechteck erstellt und dann am Ursprung \(0, 0\) positioniert.  Der Ursprung befindet sich in der oberen linken Ecke des Clientbereichs.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Durch folgenden Code wird eine Skalierungstransformation durchgeführt, die das Rechteck in x\-Richtung um den Faktor 1.75 vergrößert und es in y\-Richtung um den Faktor 0.5 verkleinert:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Das Ergebnis ist ein Rechteck, das in der x\-Richtung länger und in der y\-Richtung kürzer als das Ursprungsrechteck ist.  
  
 Um das Rechteck zu drehen, anstatt es zu skalieren, verwenden Sie folgenden Code:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Um das Rechteck zu verschieben, verwenden Sie folgenden Code:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Verwenden von Transformationen in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)