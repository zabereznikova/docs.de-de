---
title: Mond <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 6c4f24ad161302835be683e9d324ce32b16c4087
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867984"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="fa0eb-102">Module \<keyword> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa0eb-102">Module \<keyword> (Visual Basic)</span></span>

<span data-ttu-id="fa0eb-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für das aktuelle Assemblymodul gilt.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa0eb-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa0eb-104">Remarks</span></span>  

 <span data-ttu-id="fa0eb-105">Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="fa0eb-106">Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern ( `< >` ) direkt an die Deklarations Anweisung anfügen.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="fa0eb-107">Wenn ein Attribut nicht nur dem folgenden Element, sondern dem aktuellen Assemblymodul entspricht, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem- `Module` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="fa0eb-108">Wenn Sie für die gesamte Assembly gilt, verwenden Sie das [Assembly](assembly.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-108">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="fa0eb-109">Der- `Module` Modifizierer ist nicht mit der [Modul Anweisung](../statements/module-statement.md)identisch.</span><span class="sxs-lookup"><span data-stu-id="fa0eb-109">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0eb-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa0eb-110">See also</span></span>

- [<span data-ttu-id="fa0eb-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="fa0eb-111">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="fa0eb-112">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa0eb-112">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="fa0eb-113">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="fa0eb-113">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
