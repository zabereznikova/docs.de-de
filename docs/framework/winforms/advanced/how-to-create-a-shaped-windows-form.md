---
title: "Gewusst wie: Erstellen von geformten Windows&#160;Forms | Microsoft Docs"
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
  - "Formulare, Ändern der Form von"
  - "Formulare, Kreisförmig"
  - "Formulare, Benutzerdefinierte Formen"
  - "Formulare, Nicht rechteckig"
  - "Formulare, Rund"
  - "Geformte Formulare"
  - "Windows Forms, Kreisförmig"
  - "Windows Forms, Benutzerdefinierte Formen"
  - "Windows Forms, Nicht rechteckige Form"
  - "Windows Forms, Rund"
  - "Windows Forms, Geformt"
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen von geformten Windows&#160;Forms
Dieses Beispiel verleiht einem Formular eine elliptische Form, die automatisch an die Größe des Formulars angepasst wird.  
  
## Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf den <xref:System.Windows.Forms>\-Namespace und den <xref:System.Drawing>\-Namespace.  
  
 Dieses Beispiel überschreibt die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, um die Form des Formulars zu ändern.  Um diesen Code zu verwenden, kopieren Sie die Methodendeklaration sowie den Zeichencode innerhalb der Methode.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Region>   
 <xref:System.Drawing>   
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>   
 <xref:System.Windows.Forms.Control.Region%2A>   
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)