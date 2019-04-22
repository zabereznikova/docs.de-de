---
title: Assembly (Visual Basic)
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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819254"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="a1691-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1691-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="a1691-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="a1691-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1691-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1691-104">Remarks</span></span>  
 <span data-ttu-id="a1691-105">Viele Attribute beziehen sich auf ein bestimmtes Programmierelement, z. B. eine Klasse oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1691-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="a1691-106">Sie ein solches Attribut anwenden, durch Anfügen des Attributblocks in spitzen Klammern (`< >`), direkt in der deklarationsanweisung.</span><span class="sxs-lookup"><span data-stu-id="a1691-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="a1691-107">Wenn ein Attribut nicht nur auf das folgende Element, sondern für die gesamte Assembly betrifft, Sie platzieren Sie den Attributblock am Anfang der Quelldatei und identifizieren Sie das Attribut mit dem `Assembly` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a1691-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="a1691-108">Wenn es sich um das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a1691-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="a1691-109">Sie können auch ein Attribut auf eine Assembly in der AssemblyInfo.vb-Datei anwenden, in diesem Fall müssen Sie nicht mit einem Attributblock in Ihrer main Quelle-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="a1691-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1691-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1691-110">See also</span></span>

- [<span data-ttu-id="a1691-111">Module \<<schlüsselwort></span><span class="sxs-lookup"><span data-stu-id="a1691-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="a1691-112">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="a1691-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
