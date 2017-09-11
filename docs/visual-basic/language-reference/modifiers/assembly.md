---
title: Assembly (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b83102c24c80b7ee6ec4c0ffc4a446e26b7811cf
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="assembly-visual-basic"></a><span data-ttu-id="09aad-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09aad-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="09aad-103">Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="09aad-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09aad-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09aad-104">Remarks</span></span>  
 <span data-ttu-id="09aad-105">Viele Attribute beziehen sich auf ein einzelnes Programmierelement, z. B. eine Klasse oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="09aad-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="09aad-106">Sie solches Attribut anwenden, indem das Anfügen der Attributblock in spitzen Klammern (`< >`), direkt an die deklarationsanweisung.</span><span class="sxs-lookup"><span data-stu-id="09aad-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="09aad-107">Wenn ein Attribut nicht nur das folgende Element, sondern die gesamte Assembly betrifft, Sie stellen die Attributblock am Anfang der Quelldatei und kennzeichnen das Attribut mit dem `Assembly` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="09aad-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="09aad-108">Wenn sie für das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="09aad-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="09aad-109">Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo.vb anwenden, in diesem Fall müssen Sie nicht mit einem Attributblock in Ihrer main-Quellcodedateien.</span><span class="sxs-lookup"><span data-stu-id="09aad-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09aad-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09aad-110">See Also</span></span>  
 <span data-ttu-id="09aad-111">[Modul \<Schlüsselwort >](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="09aad-111">[Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="09aad-112"> [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="09aad-112"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>


