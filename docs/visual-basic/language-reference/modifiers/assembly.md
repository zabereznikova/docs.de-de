---
title: Assembly
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7d313dee1015362bd0215ed98ab7e898312cfbcd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373159"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="e1c43-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1c43-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="e1c43-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="e1c43-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1c43-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1c43-104">Remarks</span></span>  
 <span data-ttu-id="e1c43-105">Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e1c43-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="e1c43-106">Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern ( `< >` ) direkt an die Deklarations Anweisung anfügen.</span><span class="sxs-lookup"><span data-stu-id="e1c43-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="e1c43-107">Wenn sich ein Attribut nicht nur auf das folgende Element bezieht, sondern auf die gesamte Assembly, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem- `Assembly` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e1c43-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="e1c43-108">Wenn dies für das aktuelle Assemblymodul gilt, verwenden Sie das [Module](module-keyword.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e1c43-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="e1c43-109">Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo. vb anwenden. in diesem Fall müssen Sie keinen Attribut Block in der Haupt Quell Code Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1c43-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c43-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1c43-110">See also</span></span>

- [<span data-ttu-id="e1c43-111">Mond\<keyword></span><span class="sxs-lookup"><span data-stu-id="e1c43-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="e1c43-112">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="e1c43-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
