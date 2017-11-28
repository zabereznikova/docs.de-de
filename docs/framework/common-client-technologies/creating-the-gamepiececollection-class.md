---
title: Erstellen der GamePieceCollection-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: b8b53e5890aaebbad2f0a5f0e058182193b11622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="a2341-102">Erstellen der GamePieceCollection-Klasse</span><span class="sxs-lookup"><span data-stu-id="a2341-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="a2341-103">Die **GamePieceCollection**-Klasse wird von der generischen List-Klasse abgeleitet und stellt Methoden zum einfachen Verwalten von mehreren **GamePiece**-Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="a2341-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="a2341-104">Erstellen des Codes</span><span class="sxs-lookup"><span data-stu-id="a2341-104">Creating the Code</span></span>  
 <span data-ttu-id="a2341-105">Der Konstruktor der **GamePieceCollection**-Klasse initialisiert den privaten Member *capturedIndex*.</span><span class="sxs-lookup"><span data-stu-id="a2341-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="a2341-106">Dieses Feld wird zur Nachverfolgung verwendet, welche Spielelemente aktuell über die Mausaufzeichnung verfügen.</span><span class="sxs-lookup"><span data-stu-id="a2341-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="a2341-107">Die Methoden **ProcessInertia** und **Draw** vereinfachen den in den Spielmethoden [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) und [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) benötigten Code, indem sie alle Spielelemente in einer Auflistung aufzählt und die jeweilige Methode auf jedem **GamePiece**-Objekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a2341-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="a2341-108">Die **UpdateFromMouse**-Methode wird auch während der Spielaktualisierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a2341-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="a2341-109">Sie weist nur einem Spielelement die Mausaufzeichnung zu, indem zunächst geprüft wird, ob die aktuelle Aufzeichnung weiterhin aktiv ist (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="a2341-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="a2341-110">Ist dies der Fall, dürfen keine andere Elemente für die Erfassung überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a2341-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="a2341-111">Wenn aktuell kein Element über die Erfassung verfügt, zählt die **UpdateFromMouse**-Methode jedes Spielsteins (vom letzten zum ersten) auf und prüft, ob dieser Stein eine Mauserfassung meldet.</span><span class="sxs-lookup"><span data-stu-id="a2341-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="a2341-112">In diesem Fall wird dieses Element zum aktuell aufgezeichneten Element und es erfolgt keine weitere Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="a2341-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="a2341-113">Die **UpdateFromMouse**-Methode überprüft zunächst das letzte Element in der Auflistung, damit bei sich überlappenden Elementen das Element mit der höheren Z-Reihenfolge die Erfassung erhält.</span><span class="sxs-lookup"><span data-stu-id="a2341-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="a2341-114">Die Z-Reihenfolge ist weder explizit noch änderbar. Sie wird einfach durch die Reihenfolge bestimmt, in der Spielelemente zur Auflistung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a2341-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="a2341-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2341-115">See Also</span></span>  
 [<span data-ttu-id="a2341-116">Manipulationen und Trägheit</span><span class="sxs-lookup"><span data-stu-id="a2341-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="a2341-117">Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a2341-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="a2341-118">Erstellen der GamePiece-Klasse</span><span class="sxs-lookup"><span data-stu-id="a2341-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="a2341-119">Erstellen der Game1-Klasse</span><span class="sxs-lookup"><span data-stu-id="a2341-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="a2341-120">Vollständige Codeauflistungen</span><span class="sxs-lookup"><span data-stu-id="a2341-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
