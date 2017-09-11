---
title: "Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7d623a8c2276811ae443a4d745faffeeb79ffc6f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="0b2fc-102">Verwenden von Manipulationen und Trägheit in einer XNA-Anwendung</span><span class="sxs-lookup"><span data-stu-id="0b2fc-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="0b2fc-103">Dieser Artikel beschreibt, wie Sie Manipulationen und Trägheitsverarbeitung in einer Microsoft XNA-Anwendung verwenden können, um die Bewegungen von Spielelementen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="0b2fc-104">Bevor Sie diesen Artikel lesen, sollten Sie sich mit dem Thema [Manipulationen und Trägheit (Übersicht)](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) sowie mit den grundlegenden XNA-Programmierkonzepten vertraut gemacht haben.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="0b2fc-105">Um die in diesem Artikel beschriebenen Aufgaben durchführen zu können, muss Ihr XNA-Projekt auf die <xref:System.Windows.Input.Manipulations>-Assembly verweisen, und [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([Herunterladen](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) muss auf Ihrem Computer installiert sein, damit Ihr Projekt auf XNA-Assemblys verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([download](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="0b2fc-106">Funktionen im Überblick</span><span class="sxs-lookup"><span data-stu-id="0b2fc-106">Overview of Functionality</span></span>  
 <span data-ttu-id="0b2fc-107">In diesem Artikel wird gezeigt, wie Sie eine benutzerdefinierte Klasse erstellen, die ein Spielelement darstellt, das Manipulation und Trägheitsverarbeitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="0b2fc-108">Diese Klasse ermöglicht das Manipulieren eines Spielelements auf dem Bildschirm, indem es mit der Maus gezogen und die Maustaste dann losgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="0b2fc-109">Sobald die Maustaste losgelassen wurde, bewegt die Trägheitsverarbeitung das Spielelement weiter, während es nach und nach langsamer wird.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="0b2fc-110">Die Bewegung ist linear und winklig.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="0b2fc-111">![Eine einfache Anwendung mit Manipulationen und Trägheit](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GmeXna")</span><span class="sxs-lookup"><span data-stu-id="0b2fc-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="0b2fc-112">Darüber hinaus wird eine benutzerdefinierte Auflistung erstellt, die mehrere Spielelemente verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="0b2fc-113">Dies vereinfacht die Verarbeitung, die für die XNA Game-Klasse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0b2fc-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="0b2fc-114">Erstellen der GamePiece-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b2fc-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="0b2fc-115">Erstellen der GamePieceCollection-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b2fc-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="0b2fc-116">Erstellen der Game1-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b2fc-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="0b2fc-117">Vollständige Codeauflistungen</span><span class="sxs-lookup"><span data-stu-id="0b2fc-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="0b2fc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b2fc-118">See Also</span></span>  
 <span data-ttu-id="0b2fc-119"><xref:System.Windows.Input.Manipulations></span><span class="sxs-lookup"><span data-stu-id="0b2fc-119"><xref:System.Windows.Input.Manipulations></span></span>   
 [<span data-ttu-id="0b2fc-120">Überblick über Manipulationen und Trägheit</span><span class="sxs-lookup"><span data-stu-id="0b2fc-120">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)

