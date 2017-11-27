---
title: Konstruktor &#39; &lt;Namen&gt;&#39; kann nicht sich selbst aufrufen
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="deed3-102">Konstruktor &#39; &lt;Namen&gt;&#39; kann nicht sich selbst aufrufen</span><span class="sxs-lookup"><span data-stu-id="deed3-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="deed3-103">Ein `Sub New` Prozeduraufrufe in einer Klasse oder Struktur selbst.</span><span class="sxs-lookup"><span data-stu-id="deed3-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="deed3-104">Der Zweck eines Konstruktors wird eine Instanz einer Klasse initialisiert werden, oder Struktur, die beim ersten erstellt.</span><span class="sxs-lookup"><span data-stu-id="deed3-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="deed3-105">Eine Klasse oder Struktur kann mehrere Konstruktoren haben, sofern sie alle unterschiedlichen Parameterlisten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="deed3-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="deed3-106">Ein Konstruktor einen anderen Konstruktor, um seine Funktionen zusätzlich zu seiner eigenen auszuführen aufrufen darf.</span><span class="sxs-lookup"><span data-stu-id="deed3-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="deed3-107">Jedoch ist dies bedeutungslos, nach einem Konstruktor selbst aufrufen, und in der Tat vielmehr ergibt der Aufruf in einer Endlosschleife, wenn zulässig.</span><span class="sxs-lookup"><span data-stu-id="deed3-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="deed3-108">**Fehler-ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="deed3-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="deed3-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="deed3-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="deed3-110">Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="deed3-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="deed3-111">Sie sollten sich von dem des Konstruktors, die den Aufruf unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="deed3-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="deed3-112">Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufrufen, entfernen Sie die `Sub New` vollständig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="deed3-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deed3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="deed3-113">See Also</span></span>  
 [<span data-ttu-id="deed3-114">Objektlebensdauer: Erstellen und Zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="deed3-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
