---
title: "Using Manipulations and Inertia in an XNA Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Using Manipulations and Inertia in an XNA Application
Dieser Artikel beschreibt, wie Sie Manipulationen und Trägheitsverarbeitung in einer Microsoft XNA\-Anwendung verwenden können, um die Bewegungen von Spielelementen zu steuern.  Bevor Sie diesen Artikel lesen, sollten Sie sich mit dem Thema [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) vertraut gemacht haben sowie mit den grundlegenden XNA\-Programmierkonzepten.  
  
 Damit Sie die in diesem Artikel beschriebenen Aufgaben ausführen können, muss Ihr XNA\-Projekt auf die Assembly <xref:System.Windows.Input.Manipulations> \-verweisen, und Sie müssen [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) \([Herunterladen](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)\) auf Ihrem Computer installiert haben, damit Ihr Projekt auf die XNA\-Assemblys verweisen kann.  
  
## Funktionen im Überblick  
 In diesem Artikel wird gezeigt, wie Sie eine benutzerdefinierte Klasse erstellen, die ein Spielelement darstellt, das Manipulation und Trägheitsverarbeitung verwendet.  Diese Klasse ermöglicht das Manipulieren eines Spielelements auf dem Bildschirm, indem es mit der Maus gezogen und die Maustaste dann losgelassen wird.  Sobald die Maustaste losgelassen wurde, bewegt die Trägheitsverarbeitung das Spielelement weiter, während es nach und nach langsamer wird.  Die Bewegung ist linear und winklig.  
  
 ![Eine einfache Anwendung mit Manipulationen und Trägheit.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.png "NDP\_GameXna")  
  
 Darüber hinaus wird eine benutzerdefinierte Auflistung erstellt, die mehrere Spielelemente verwaltet.  Dies vereinfacht die Verarbeitung, die für die XNA Game\-Klasse erforderlich ist.  
  
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## Siehe auch  
 <xref:System.Windows.Input.Manipulations>   
 [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)