---
title: "Gewusst wie: Ausf&#252;llen offener K&#246;rper | Microsoft Docs"
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
  - "Figuren, Füllen"
  - "Offene Figuren, Füllen"
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Ausf&#252;llen offener K&#246;rper
Sie können einen Pfad ausfüllen, indem Sie ein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt an die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode übergeben.  Die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode füllt den Pfad entsprechend dem Füllmodus \(**Alternate** oder **Winding**\) aus, der derzeit für den Pfad festgelegt ist.  Falls der Pfad offene Körper enthält, wird er so ausgefüllt, als wären diese Körper geschlossen.  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] wird ein Körper geschlossen, indem eine gerade Linie vom Endpunkt zum Anfangspunkt gezogen wird.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Pfad erstellt, der aus einer offenen Figur \(einem Bogen\) und einer geschlossenen Figur \(einer Ellipse\) besteht.  Die <xref:System.Drawing.Graphics.FillPath%2A>\-Methode füllt den Pfad entsprechend dem Standardfüllmodus, der <xref:System.Drawing.Drawing2D.FillMode> lautet.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.  Beachten Sie, dass der Pfad \(entsprechend dem Füllmodus <xref:System.Drawing.Drawing2D.FillMode>\) so ausgefüllt wird, als wäre der offene Körper durch eine gerade Linie zwischen ihrem Endpunkt und ihrem Anfangspunkt geschlossen.  
  
 ![Offenen Pfad ausfüllen](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Grafikpfade in GDI\+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)