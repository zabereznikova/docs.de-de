---
title: "Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="cc3f4-102">Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="cc3f4-103">Eine Prozedur ist mit einem optionalen Parameter deklariert, der einen Typparameter, der nicht eingeschränkt wird verwendet, um ein Verweistyp sein muss.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="cc3f4-104">Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="cc3f4-105">Wenn der Parameter ein Verweistyp ist, muss der optionale Wert `Nothing`, dies ist ein gültiger Wert für jeden Referenztyp.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="cc3f4-106">Wenn der Parameter ein Werttyp ist, muss dieses Typs einen elementaren Datentyp, der vom Visual Basic vordefiniert sein.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="cc3f4-107">Dies ist, da Sie ein zusammengesetzten Werttyp aufweist, z. B. eine benutzerdefinierte Struktur keine gültigen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="cc3f4-108">Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass sie einen Verweistyp zum Vermeiden eines Werttyps verfügt über keinen gültigen Standardwert aufweist.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="cc3f4-109">Dies bedeutet, Sie müssen dem Typparameter entweder durch Einschränken der `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="cc3f4-110">**Fehler-ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="cc3f4-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc3f4-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cc3f4-111">To correct this error</span></span>  
  
-   <span data-ttu-id="cc3f4-112">Schränken Sie den Typparameter um nur den Verweistyp akzeptiert, oder verwenden Sie es nicht für den optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="cc3f4-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3f4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc3f4-113">See Also</span></span>  
 [<span data-ttu-id="cc3f4-114">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc3f4-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="cc3f4-115">Typliste</span><span class="sxs-lookup"><span data-stu-id="cc3f4-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="cc3f4-116">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cc3f4-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="cc3f4-117">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="cc3f4-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="cc3f4-118">Strukturen</span><span class="sxs-lookup"><span data-stu-id="cc3f4-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="cc3f4-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="cc3f4-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
