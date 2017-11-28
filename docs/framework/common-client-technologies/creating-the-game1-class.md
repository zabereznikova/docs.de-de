---
title: Erstellen der Game1-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 1e4fd15013f10667b397e010fff56b7bc6a0f641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="7f4dd-102">Erstellen der Game1-Klasse</span><span class="sxs-lookup"><span data-stu-id="7f4dd-102">Creating the Game1 Class</span></span>
<span data-ttu-id="7f4dd-103">Wie bei allen Microsoft XNA-Projekten ist die Game1-Klasse von der [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx)-Klasse abgeleitet, die die Initialisierung von einfachen Grafikgeräten, die Spiellogik und das Rendern von Code für XNA-Spiele bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="7f4dd-104">Die Game1-Klasse ist recht einfach, da die meiste Arbeit in den Klassen "GamePiece" und "GamePieceCollection" erledigt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="7f4dd-105">Erstellen des Codes</span><span class="sxs-lookup"><span data-stu-id="7f4dd-105">Creating the Code</span></span>  
 <span data-ttu-id="7f4dd-106">Die privaten Member der Klasse bestehe aus einem **GamePieceCollection**-Objekt, das die Spielsteine enthält, einem [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx)-Objekt und einem [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx)-Objekt zum Rendern von Spielsteinen.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="7f4dd-107">Während der Spielinitialisierung werden diese Objekte instanziiert.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="7f4dd-108">Wenn die [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx)-Methode aufgerufen wird, werden die Spielsteine erstellt und einem **GamePieceCollection**-Objekt zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="7f4dd-109">Es gibt zwei Typen von Spielsteinen:</span><span class="sxs-lookup"><span data-stu-id="7f4dd-109">There are two types of game pieces.</span></span> <span data-ttu-id="7f4dd-110">Der Skalierungsfaktor für die Spielsteine wird leicht geändert, sodass es einige kleinere und einige größere Spielsteine gibt.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="7f4dd-111">Die [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)-Methode wird beim Ausführen des Spiels wiederholt von XNA Framework aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="7f4dd-112">Die [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)-Methode ruft die Methoden **ProcessInertia** und **UpdateFromMouse** in der Auflistung der Spielsteine auf.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="7f4dd-113">Diese Methoden sind unter [Creating the GamePieceCollection Class (Erstellen der GamePieceCollection-Klasse)](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="7f4dd-114">Die [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)-Methode wird beim Ausführen des Spiels ebenfalls wiederholt von XNA Framework aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="7f4dd-115">Die [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)-Methode rendert Spielsteine, indem sie die **Draw**-Methode des **GamePieceCollection**-Objekts aufruft.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="7f4dd-116">Diese Methode ist unter [Creating the GamePieceCollection Class (Erstellen der GamePieceCollection-Klasse)](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f4dd-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="7f4dd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f4dd-117">See Also</span></span>  
 [<span data-ttu-id="7f4dd-118">Manipulationen und Trägheit</span><span class="sxs-lookup"><span data-stu-id="7f4dd-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="7f4dd-119">Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung</span><span class="sxs-lookup"><span data-stu-id="7f4dd-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="7f4dd-120">Erstellen der GamePiece-Klasse</span><span class="sxs-lookup"><span data-stu-id="7f4dd-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="7f4dd-121">Erstellen der GamePieceCollection-Klasse</span><span class="sxs-lookup"><span data-stu-id="7f4dd-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="7f4dd-122">Vollständige Codeauflistungen</span><span class="sxs-lookup"><span data-stu-id="7f4dd-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
