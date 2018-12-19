---
title: Operatorschlüsselwörter – C#-Referenz
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- keywords [C#], operators
- operators [C#], keywords
ms.assetid: f745c81f-f8d8-4673-86a1-0f3a85cc63c3
ms.openlocfilehash: e03e1c930b452cf5e4f2c4bb1d06d5363f20c991
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243606"
---
# <a name="operator-keywords-c-reference"></a><span data-ttu-id="b18c4-102">Operatorschlüsselwörter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b18c4-102">Operator Keywords (C# Reference)</span></span>

<span data-ttu-id="b18c4-103">Werden verwendet, um verschiedene Aktionen auszuführen wie das Erstellen von Objekten, das Überprüfen des Laufzeittyps eines Objekts, das Abrufen der Größe eines Typs usw.</span><span class="sxs-lookup"><span data-stu-id="b18c4-103">Used to perform miscellaneous actions such as creating objects, checking the run-time type of an object, obtaining the size of a type, and other actions.</span></span> <span data-ttu-id="b18c4-104">In diesem Abschnitt werden die folgenden Schlüsselwörter beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b18c4-104">This section introduces the following keywords:</span></span>

- <span data-ttu-id="b18c4-105">[as](as.md) Konvertiert ein Objekt in einen kompatiblen Typ</span><span class="sxs-lookup"><span data-stu-id="b18c4-105">[as](as.md) Converts an object to a compatible type.</span></span>

- <span data-ttu-id="b18c4-106">[await](await.md) Hält eine [asynchrone](async.md) Methode an, bis eine erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b18c4-106">[await](await.md) Suspends an [async](async.md) method until an awaited task is completed.</span></span>

- <span data-ttu-id="b18c4-107">[is](is.md) Überprüft den Laufzeittyp eines Objekts oder (ab C# 7.0) überprüft einen Ausdruck anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="b18c4-107">[is](is.md) Checks the run-time type of an object, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

- [<span data-ttu-id="b18c4-108">new</span><span class="sxs-lookup"><span data-stu-id="b18c4-108">new</span></span>](new.md)

  - <span data-ttu-id="b18c4-109">[new-Operator](new-operator.md) Erstellt Objekte</span><span class="sxs-lookup"><span data-stu-id="b18c4-109">[new Operator](new-operator.md) Creates objects.</span></span>

  - <span data-ttu-id="b18c4-110">[new-Modifizierer](new-modifier.md) Blendet einen geerbten Member aus</span><span class="sxs-lookup"><span data-stu-id="b18c4-110">[new Modifier](new-modifier.md) Hides an inherited member.</span></span>

  - <span data-ttu-id="b18c4-111">[new-Einschränkung](new-constraint.md) Qualifiziert einen Typparameter</span><span class="sxs-lookup"><span data-stu-id="b18c4-111">[new Constraint](new-constraint.md) Qualifies a type parameter.</span></span>

- <span data-ttu-id="b18c4-112">[nameof](nameof.md) Ruft den einfachen (nicht qualifizierten) Zeichenfolgennamen einer Variablen, eines Typs oder eines Members ab</span><span class="sxs-lookup"><span data-stu-id="b18c4-112">[nameof](nameof.md) Obtains the simple (unqualified) string name of a variable, type, or member.</span></span>

- <span data-ttu-id="b18c4-113">[sizeof](sizeof.md) Ruft die Größe eines nicht verwalteten Typs ab.</span><span class="sxs-lookup"><span data-stu-id="b18c4-113">[sizeof](sizeof.md) Obtains the size of an unmanaged type.</span></span>  

- <span data-ttu-id="b18c4-114">[typeof](typeof.md) Ruft das <xref:System.Type?displayProperty=nameWithType>-Objekt für einen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="b18c4-114">[typeof](typeof.md) Obtains the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span>  

- [<span data-ttu-id="b18c4-115">true</span><span class="sxs-lookup"><span data-stu-id="b18c4-115">true</span></span>](true.md)  

  - <span data-ttu-id="b18c4-116">[true-Operator](true-false-operators.md) Gibt den [bool](bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „true“ hat.</span><span class="sxs-lookup"><span data-stu-id="b18c4-116">[true Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely true.</span></span>

  - <span data-ttu-id="b18c4-117">[true-Literal](true-literal.md) Stellt den [bool](bool.md)-Wert `true` dar.</span><span class="sxs-lookup"><span data-stu-id="b18c4-117">[true Literal](true-literal.md) Represents the [bool](bool.md) value `true`.</span></span>

- [<span data-ttu-id="b18c4-118">false</span><span class="sxs-lookup"><span data-stu-id="b18c4-118">false</span></span>](false.md)  

  - <span data-ttu-id="b18c4-119">[false-Operator](true-false-operators.md) Gibt den [bool](bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „false“ hat.</span><span class="sxs-lookup"><span data-stu-id="b18c4-119">[false Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely false.</span></span>

  - <span data-ttu-id="b18c4-120">[false-Literal](false-literal.md) Stellt den [bool](bool.md)-Wert `false` dar.</span><span class="sxs-lookup"><span data-stu-id="b18c4-120">[false Literal](false-literal.md) Represents the [bool](bool.md) value `false`.</span></span>

- <span data-ttu-id="b18c4-121">[stackalloc](stackalloc.md) Belegt einen Speicherblock auf dem Stapel</span><span class="sxs-lookup"><span data-stu-id="b18c4-121">[stackalloc](stackalloc.md) Allocates a block of memory on the stack.</span></span>  

<span data-ttu-id="b18c4-122">Die folgenden Schlüsselwörter, die als Operatoren und Anweisungen verwendet werden können, finden Sie im Abschnitt [Anweisungen](statement-keywords.md):</span><span class="sxs-lookup"><span data-stu-id="b18c4-122">The following keywords, which can be used as operators and as statements, are covered in the [Statements](statement-keywords.md) section:</span></span>

- <span data-ttu-id="b18c4-123">[checked](checked.md) Gibt einen geprüften Kontext an</span><span class="sxs-lookup"><span data-stu-id="b18c4-123">[checked](checked.md) Specifies checked context.</span></span>  

- <span data-ttu-id="b18c4-124">[unchecked](unchecked.md) Gibt einen ungeprüften Kontext an</span><span class="sxs-lookup"><span data-stu-id="b18c4-124">[unchecked](unchecked.md) Specifies unchecked context.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b18c4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b18c4-125">See also</span></span>

- [<span data-ttu-id="b18c4-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b18c4-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b18c4-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b18c4-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b18c4-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b18c4-128">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b18c4-129">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b18c4-129">C# Operators</span></span>](../operators/index.md)
