---
title: Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159676"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="96735-102">BC30024: die Anweisung ist innerhalb einer Methode/eines mehrzeiligen Lambda-Ausdrucks ungültig.</span><span class="sxs-lookup"><span data-stu-id="96735-102">BC30024: Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="96735-103">Die-Anweisung ist in einer-,-,-oder-Eigenschaften `Sub` `Function` Prozedur ungültig `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="96735-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="96735-104">Einige-Anweisungen können auf Modul-oder Klassenebene platziert werden.</span><span class="sxs-lookup"><span data-stu-id="96735-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="96735-105">Andere, wie z `Option Strict` . b., müssen sich auf der Namespace Ebene befinden und vor allen anderen Deklarationen stehen.</span><span class="sxs-lookup"><span data-stu-id="96735-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>

 <span data-ttu-id="96735-106">**Fehler-ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="96735-106">**Error ID:** BC30024</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="96735-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="96735-107">To correct this error</span></span>

- <span data-ttu-id="96735-108">Entfernen Sie die-Anweisung aus der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="96735-108">Remove the statement from the procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="96735-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96735-109">See also</span></span>

- [<span data-ttu-id="96735-110">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="96735-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="96735-111">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="96735-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="96735-112">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="96735-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="96735-113">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="96735-113">Set Statement</span></span>](../statements/set-statement.md)
