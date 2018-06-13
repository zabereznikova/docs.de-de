---
title: Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cf5d3e16c43920a90b69c815f91601c6d33c845d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638370"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="9b8ae-102">Die Verwendung der Standardinstanz einer Klasse im Klassenkonstruktor kann zu einem unendlichen rekursiven Aufruf führen.</span><span class="sxs-lookup"><span data-stu-id="9b8ae-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="9b8ae-103">Eine Standardinstanz einer Klasse wurde im Konstruktor der Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b8ae-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="9b8ae-104">Dies kann zu einem unendlichen rekursiven Aufruf, auch bekannt als Endlosschleife, führen.</span><span class="sxs-lookup"><span data-stu-id="9b8ae-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b8ae-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9b8ae-105">To correct this error</span></span>  
  
-   <span data-ttu-id="9b8ae-106">Entfernen Sie die Standardinstanz aus dem Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="9b8ae-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8ae-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b8ae-107">See Also</span></span>  
 [<span data-ttu-id="9b8ae-108">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="9b8ae-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
