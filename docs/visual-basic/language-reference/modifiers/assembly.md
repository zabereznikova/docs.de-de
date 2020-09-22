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
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875532"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="7415c-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7415c-102">Assembly (Visual Basic)</span></span>

<span data-ttu-id="7415c-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="7415c-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7415c-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7415c-104">Remarks</span></span>  

 <span data-ttu-id="7415c-105">Viele Attribute beziehen sich auf ein einzelnes Programmier Element, z. b. eine Klasse oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7415c-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="7415c-106">Sie wenden ein derartiges Attribut an, indem Sie den Attribut Block in spitzen Klammern ( `< >` ) direkt an die Deklarations Anweisung anfügen.</span><span class="sxs-lookup"><span data-stu-id="7415c-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="7415c-107">Wenn sich ein Attribut nicht nur auf das folgende Element bezieht, sondern auf die gesamte Assembly, platzieren Sie den-Attribut Block am Anfang der Quelldatei und identifizieren das-Attribut mit dem- `Assembly` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7415c-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="7415c-108">Wenn dies für das aktuelle Assemblymodul gilt, verwenden Sie das [Module](module-keyword.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7415c-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="7415c-109">Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo. vb anwenden. in diesem Fall müssen Sie keinen Attribut Block in der Haupt Quell Code Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="7415c-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7415c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7415c-110">See also</span></span>

- [<span data-ttu-id="7415c-111">Mond \<keyword></span><span class="sxs-lookup"><span data-stu-id="7415c-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="7415c-112">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="7415c-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
