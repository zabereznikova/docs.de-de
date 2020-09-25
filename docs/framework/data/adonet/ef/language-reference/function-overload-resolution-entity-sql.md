---
title: Auflösung von Funktionsüberladungen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: d37cd9342d1fb3b60d5a2c05d373fb7e71f54b1f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189395"
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="b551a-102">Auflösung von Funktionsüberladungen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b551a-102">Function Overload Resolution (Entity SQL)</span></span>

<span data-ttu-id="b551a-103">In diesem Thema wird beschrieben, wie [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b551a-103">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="b551a-104">Solange die Funktionen über eindeutige Signaturen verfügen, können mehrere Funktionen mit demselben Namen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b551a-104">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="b551a-105">Wenn das der Fall ist, muss anhand folgender Kriterien ermittelt werden, auf welche Funktion durch einen gegebenen Ausdruck verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b551a-105">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="b551a-106">Diese Kriterien werden nacheinander überprüft.</span><span class="sxs-lookup"><span data-stu-id="b551a-106">These criteria are applied in sequence.</span></span> <span data-ttu-id="b551a-107">Das erste Kriterium, das nur für eine Funktion gilt, kennzeichnet die aufgelöste Funktion.</span><span class="sxs-lookup"><span data-stu-id="b551a-107">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1. <span data-ttu-id="b551a-108">**Parameter Nummer**.</span><span class="sxs-lookup"><span data-stu-id="b551a-108">**Parameter number**.</span></span> <span data-ttu-id="b551a-109">Die Funktion verfügt über dieselbe Anzahl von Parametern wie der angegebene Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b551a-109">The function has the same number of parameters specified in the expression.</span></span>  
  
2. <span data-ttu-id="b551a-110">**Exakte Entsprechung für Typ**.</span><span class="sxs-lookup"><span data-stu-id="b551a-110">**Exact match on type**.</span></span> <span data-ttu-id="b551a-111">Jeder Argumenttyp der Funktion stimmt genau mit dem Parametertyp überein oder ist das NULL-Literal.</span><span class="sxs-lookup"><span data-stu-id="b551a-111">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3. <span data-ttu-id="b551a-112">Entsprechung **für den Untertyp**.</span><span class="sxs-lookup"><span data-stu-id="b551a-112">**Match on subtype**.</span></span> <span data-ttu-id="b551a-113">Jeder Argumenttyp der Funktion stimmt mit dem Parametertyp genau überein, ist ein Untertyp des Parametertyps, oder das Argument besteht aus dem NULL-Literal.</span><span class="sxs-lookup"><span data-stu-id="b551a-113">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="b551a-114">Wenn sich mehrere Funktionen nur in der Anzahl der erforderlichen Untertypkonvertierungen unterscheiden, ist die Funktion mit der geringsten Anzahl an Untertypkonvertierungen die aufgelöste Funktion.</span><span class="sxs-lookup"><span data-stu-id="b551a-114">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4. <span data-ttu-id="b551a-115">Entsprechung **für den Untertyp oder die Typerweiterung**.</span><span class="sxs-lookup"><span data-stu-id="b551a-115">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="b551a-116">Jeder Argumenttyp der Funktion stimmt mit dem Parametertyp genau überein, ist ein Untertyp des Parametertyps, kann auf den Parametertyp heraufgestuft werden, oder das Argument besteht aus dem NULL-Literal.</span><span class="sxs-lookup"><span data-stu-id="b551a-116">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="b551a-117">Auch hier gilt: Wenn sich mehrere Funktionen nur in der Anzahl der Untertypkonvertierungen und Heraufstufungen unterscheiden, ist die Funktion mit der geringsten Anzahl an Untertypkonvertierungen und Heraufstufungen die aufgelöste Funktion.</span><span class="sxs-lookup"><span data-stu-id="b551a-117">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="b551a-118">Wenn keine Funktion anhand der Kriterien ausgewählt werden kann, ist der Ausdruck zum Aufruf der Funktion mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="b551a-118">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="b551a-119">Auch wenn eine Funktion mithilfe dieser Regeln ermittelt werden kann, stimmen die Argumente dennoch möglicherweise nicht mit den Parametern überein.</span><span class="sxs-lookup"><span data-stu-id="b551a-119">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="b551a-120">In diesem Fall wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b551a-120">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="b551a-121">Bei benutzerdefinierten Funktionen hat die Definition für eine Inlineabfragefunktion Vorrang, selbst wenn eine vom Modell definierte Funktion eine Signatur aufweist, die besser für die benutzerdefinierte Funktion geeignet wäre.</span><span class="sxs-lookup"><span data-stu-id="b551a-121">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b551a-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b551a-122">See also</span></span>

- [<span data-ttu-id="b551a-123">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b551a-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b551a-124">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b551a-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="b551a-125">Funktionen</span><span class="sxs-lookup"><span data-stu-id="b551a-125">Functions</span></span>](functions-entity-sql.md)
