---
title: "Gewusst wie: Ausf&#252;llen einer Form mit einer Schraffur | Microsoft Docs"
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
  - "Pinsel, Verwenden von Schraffurpinseln"
  - "Muster, Hinzufügen zu Formen"
  - "Formen, Füllen mit Mustern"
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Ausf&#252;llen einer Form mit einer Schraffur
Eine Schraffur besteht aus zwei Farben: einer für den Hintergrund und einer anderen für die Linien, die das Muster auf dem Hintergrund bilden.  Um eine geschlossene Form mit einer Schraffur auszufüllen, verwenden Sie ein <xref:System.Drawing.Drawing2D.HatchBrush>\-Objekt.  Im folgenden Beispiel wird gezeigt, wie Sie eine Ellipse mit einer Schraffur füllen:  
  
## Beispiel  
 Der <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>\-Konstruktor enthält drei Argumente: den Schraffurstil, die Farbe der Schraffurlinie und die Farbe des Hintergrunds.  Das Schraffurstilargument kann ein beliebiger Wert aus der <xref:System.Drawing.Drawing2D.HatchStyle>\-Enumeration sein.  Die <xref:System.Drawing.Drawing2D.HatchStyle>\-Enumeration enthält mehr als 50 Elemente. Einige davon sind im Folgenden aufgelistet:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
 In der folgenden Abbildung ist die ausgefüllte Ellipse dargestellt.  
  
 ![Schraffur](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)