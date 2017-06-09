---
title: "Gewusst wie: Ausschneiden mit einem Bereich | Microsoft Docs"
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
  - "Bereiche, Clipping"
  - "Bereiche, Einschränken der Zeichenoberfläche"
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Ausschneiden mit einem Bereich
Der Clipbereich ist eine der Eigenschaften der <xref:System.Drawing.Graphics>\-Klasse.  Alle von einem bestimmten <xref:System.Drawing.Graphics>\-Objekt ausgeführten Zeichenvorgänge sind auf den Clipbereich des jeweiligen <xref:System.Drawing.Graphics>\-Objekts beschränkt.  Der Clipbereich kann durch Aufrufen der <xref:System.Drawing.Graphics.SetClip%2A>\-Methode festgelegt werden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Pfad erstellt, der aus einem einzelnen Polygon besteht.  Anschließend wird durch den Code ein auf diesem Pfad basierender Bereich erstellt.  Zunächst wird der Bereich an die <xref:System.Drawing.Graphics.SetClip%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts übergeben, und anschließend werden zwei Zeichenfolgen gezeichnet.  
  
 In der folgenden Abbildung sind die abgeschnittenen Zeichenfolgen dargestellt.  
  
 ![Zuschneiden](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Bereiche in GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)