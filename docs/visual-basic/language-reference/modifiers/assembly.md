---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="84d4d-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84d4d-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="84d4d-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="84d4d-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d4d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84d4d-104">Remarks</span></span>  
 <span data-ttu-id="84d4d-105">Viele Attribute beziehen sich auf ein einzelnes Programmierelement, z. B. eine Klasse oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="84d4d-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="84d4d-106">Sie solches Attribut anwenden, indem anfügen Attributblocks in spitzen Klammern (`< >`), direkt in der deklarationsanweisung.</span><span class="sxs-lookup"><span data-stu-id="84d4d-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="84d4d-107">Wenn ein Attribut nicht nur auf das folgende Element, sondern die gesamte Assembly betrifft, Sie platzieren Sie den Attributblock am Anfang der Quelldatei und identifizieren Sie das Attribut mit dem `Assembly` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="84d4d-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="84d4d-108">Wenn sie für das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="84d4d-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="84d4d-109">Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo.vb anwenden, in diesem Fall müssen Sie keinen Attributblock in Ihrer wichtigsten Quellcode-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="84d4d-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d4d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84d4d-110">See Also</span></span>  
 [<span data-ttu-id="84d4d-111">Module \<<schlüsselwort></span><span class="sxs-lookup"><span data-stu-id="84d4d-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="84d4d-112">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="84d4d-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

