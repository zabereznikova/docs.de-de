---
title: "Creating the GamePieceCollection Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the GamePieceCollection Class
Die **GamePieceCollection**\-Klasse wird von der generischen List\-Klasse abgeleitet und stellt Methoden zum einfachen Verwalten von mehreren **GamePiece**\-Objekten bereit.  
  
## Erstellen des Codes  
 Der Konstruktor der **GamePieceCollection**\-Klasse initialisiert den privaten Member *capturedIndex*.  Dieses Feld wird zur Nachverfolgung verwendet, welche Spielelemente aktuell über die Mausaufzeichnung verfügen.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 Die Methoden **ProcessInertia** und **Draw** vereinfachen den in den Spielmethoden [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) und [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) erforderlichen Code, indem alle Spielelemente in der Auflistung aufgezählt werden. Zudem wird die entsprechende Methode für jedes **GamePiece**\-Objekt aufgerufen.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 Die **UpdateFromMouse**\-Methode wird auch während der Spielaktualisierung aufgerufen.  Sie weist nur einem Spielelement die Mausaufzeichnung zu, indem zunächst geprüft wird, ob die aktuelle Aufzeichnung weiterhin aktiv ist \(sofern vorhanden\).  Ist dies der Fall, dürfen keine andere Elemente für die Erfassung überprüft werden.  
  
 Wenn aktuell kein Element über die Aufzeichnung verfügt, zählt die **UpdateFromMouse**\-Methode jedes Spielelement \(vom letzten zum ersten\) auf und prüft, ob dieses Element eine Mausaufzeichnung meldet.  In diesem Fall wird dieses Element zum aktuell aufgezeichneten Element und es erfolgt keine weitere Verarbeitung.  Die **UpdateFromMouse**\-Methode überprüft zunächst das letzte Element in der Auflistung, damit bei sich überlappenden Elementen das Element mit der höheren Z\-Reihenfolge die Aufzeichnung erhält.  Die Z\-Reihenfolge ist weder explizit noch änderbar. Sie wird einfach durch die Reihenfolge bestimmt, in der Spielelemente zur Auflistung hinzugefügt werden.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## Siehe auch  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)