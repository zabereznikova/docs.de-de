---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a><span data-ttu-id="524d5-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="524d5-102">Default (Visual Basic)</span></span>
<span data-ttu-id="524d5-103">Gibt eine Eigenschaft als Standardeigenschaft von der Klasse, Struktur oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="524d5-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="524d5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="524d5-104">Remarks</span></span>  
 <span data-ttu-id="524d5-105">Eine Klasse, Struktur oder Schnittstelle kann höchstens eine seiner Eigenschaften als Festlegen der *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter übernimmt.</span><span class="sxs-lookup"><span data-stu-id="524d5-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="524d5-106">Wenn der Code einen Verweis auf eine Klasse oder Struktur vornimmt, ohne dass ein Element, löst Visual Basic, Verweis auf die Standardeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="524d5-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="524d5-107">Standardeigenschaften können dazu führen, eine kleine Verkleinerung an Code Quellzeichen können, sie jedoch Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="524d5-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="524d5-108">Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur enthält kann nicht bestimmte darauf, ob der Verweis der Klasse oder Struktur selbst oder eine Standardeigenschaft greift auf.</span><span class="sxs-lookup"><span data-stu-id="524d5-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="524d5-109">Dies kann zu Compilerfehlern oder geringfügige Logikfehler zur Laufzeit führen.</span><span class="sxs-lookup"><span data-stu-id="524d5-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="524d5-110">Sie können das Risiko von Fehlern der Standard-Eigenschaft etwas reduzieren, indem immer mithilfe der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp das Einchecken festlegen `On`.</span><span class="sxs-lookup"><span data-stu-id="524d5-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="524d5-111">Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist was seinen Namen aus.</span><span class="sxs-lookup"><span data-stu-id="524d5-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="524d5-112">Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="524d5-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="524d5-113">Für die Lesbarkeit des Codes sollten Sie auch sollten Sie immer alle Eigenschaften explizit auf, auch die Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="524d5-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="524d5-114">Die `Default` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="524d5-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="524d5-115">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="524d5-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="524d5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="524d5-116">See Also</span></span>  
 [<span data-ttu-id="524d5-117">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="524d5-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="524d5-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="524d5-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
