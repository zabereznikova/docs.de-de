---
title: Struktur &#39; &lt;Strukturname&gt;&#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet &#39; enthalten Benutzerdefinierte &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="50ab5-102">Struktur &#39; &lt;Strukturname&gt;&#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet &#39; enthalten Benutzerdefinierte &#39;</span><span class="sxs-lookup"><span data-stu-id="50ab5-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="50ab5-103">Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="50ab5-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="50ab5-104">Jede Struktur benötigen, eine Variable oder ein Ereignis, das für jede spezifische Instanz (nicht freigegebene) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="50ab5-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="50ab5-105">Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht.</span><span class="sxs-lookup"><span data-stu-id="50ab5-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="50ab5-106">Darüber hinaus treten keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis, das Ereignis nicht mit einem `Custom` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="50ab5-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="50ab5-107">**Fehler-ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="50ab5-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50ab5-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="50ab5-108">To correct this error</span></span>  
  
-   <span data-ttu-id="50ab5-109">Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`.</span><span class="sxs-lookup"><span data-stu-id="50ab5-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="50ab5-110">Wenn Sie nur ein Ereignis definieren, muss es sowohl nicht benutzerdefinierte als auch nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="50ab5-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ab5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50ab5-111">See Also</span></span>  
 [<span data-ttu-id="50ab5-112">Strukturen</span><span class="sxs-lookup"><span data-stu-id="50ab5-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="50ab5-113">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="50ab5-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="50ab5-114">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="50ab5-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
