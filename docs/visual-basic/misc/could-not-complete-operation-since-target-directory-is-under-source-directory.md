---
title: Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: fca42f91f803a6b12535badcb25cc05cc3d23f6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598469"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="1db58-102">Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.</span><span class="sxs-lookup"><span data-stu-id="1db58-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="1db58-103">Ein zyklischer Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="1db58-103">A cyclic operation has failed.</span></span> <span data-ttu-id="1db58-104">Ein zyklischer Vorgang wird zyklisch ausgeführt und kann daher nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1db58-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="1db58-105">Beispielsweise könnte Objekt A versuchen, von Objekt B zu erben, das wiederum versucht, von Objekt A zu erben.</span><span class="sxs-lookup"><span data-stu-id="1db58-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1db58-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1db58-106">To correct this error</span></span>  
  
- <span data-ttu-id="1db58-107">Wenn geerbt wird, müssen Sie sicherstellen, dass keine zyklischen Verweise vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1db58-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db58-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1db58-108">See also</span></span>

- [<span data-ttu-id="1db58-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="1db58-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="1db58-110">Verwenden von Haltepunkten in Visual Studio-debugger</span><span class="sxs-lookup"><span data-stu-id="1db58-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
