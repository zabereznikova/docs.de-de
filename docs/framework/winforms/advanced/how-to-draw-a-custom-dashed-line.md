---
title: "Gewusst wie: Zeichnen einer benutzerdefinierten gestrichelten Linie | Microsoft Docs"
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
  - "Linien, Benutzerdefiniert"
  - "Linien, Gestrichelt"
  - "Linien, Zeichnen"
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Zeichnen einer benutzerdefinierten gestrichelten Linie
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehrere Stile für gestrichelte Linien bereit, die in der <xref:System.Drawing.Drawing2D.DashStyle>\-Enumeration enthalten sind.  Wenn diese Standardstile Ihren Anforderungen nicht entsprechen, können Sie auch ein benutzerdefiniertes Strichmuster erstellen.  
  
## Beispiel  
 Um eine benutzerdefinierte gestrichelte Linie zu zeichnen, ordnen Sie die Strichlängen sowie ihre Abstände in einem Array an und weisen das Array der <xref:System.Drawing.Pen.DashPattern%2A>\-Eigenschaft eines <xref:System.Drawing.Pen>\-Objekts als Wert zu.  Im folgenden Beispiel wird eine benutzerdefinierte gestrichelte Linie auf der Grundlage des Arrays  `{5, 2, 15, 4}` gezeichnet.  Wenn Sie die Arrayelemente mit der Stiftbreite 5 multiplizieren, erhalten Sie `{25, 10, 75, 20}`.  Die angezeigten Striche sind abwechselnd 25 und 75 Einheiten lang, und die Abstände sind abwechselnd 10 und 20 Einheiten lang.  
  
 In der folgenden Abbildung ist die resultierende gestrichelte Linie dargestellt.  Beachten Sie, dass der letzte Strich der Linie maximal 25 Einheiten betragen darf, damit die Linie bei \(405, 5\) endet.  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens6.png "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## Kompilieren des Codes  
 Erstellen Sie ein Windows Form, und verarbeiten Sie das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars.  Fügen Sie den vorangehenden Code in den <xref:System.Windows.Forms.Control.Paint>\-Ereignishandler ein.  
  
## Siehe auch  
 [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)