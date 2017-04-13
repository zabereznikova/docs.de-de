---
title: "Creating the Game1 Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the Game1 Class
Wie bei allen Microsoft XNA\-Projekten ist die Game1\-Klasse aus der [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx)\-Klasse abgeleitet, die die grundlegende Initialisierung für Grafikgeräte, die Spiellogik und den Renderingcode für XNA\-Spiele bereitstellt.  Die Game1\-Klasse ist recht einfach, da die meiste Arbeit in den Klassen "GamePiece" und "GamePieceCollection" erledigt wird.  
  
## Erstellen des Codes  
 Die privaten Member für die Klasse bestehen aus einem **GamePieceCollection**\-Objekt, das die Spielsteine aufnimmt, einem [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx)\-Objekt, und einem [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx)\-Objekt, mit dem die Spielsteine gerendert werden.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Während der Spielinitialisierung werden diese Objekte instanziiert.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 Wenn die [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx)\-Methode aufgerufen wird, werden die Spielsteine erstellt und dem **GamePieceCollection**\-Objekt zugewiesen.  Es gibt zwei Typen von Spielsteinen:  Der Skalierungsfaktor für die Spielsteine wird leicht geändert, sodass es einige kleinere und einige größere Spielsteine gibt.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 Die [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)\-Methode wird vom XNA Framework während der Ausführung des Spiels wiederholt aufgerufen.  Die [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)\-Methode ruft **ProcessInertia**\- und die **UpdateFromMouse**\-Methode der Spielsteinauflistung auf.  Diese Methoden sind unter [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) beschrieben.  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 Die [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)\-Methode wird vom XNA Framework während der Ausführung des Spiels ebenfalls wiederholt aufgerufen.  Die [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)\-Methode führt das Rendern der Spielsteine aus, indem sie die **Draw**\-Methode des **GamePieceCollection**\-Objekts aufruft.  Diese Methode ist unter [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) beschrieben.  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## Siehe auch  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)