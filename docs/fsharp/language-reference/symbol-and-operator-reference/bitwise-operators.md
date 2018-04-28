---
title: Bitweise Operatoren (F#)
description: Erfahren Sie, bis die bitweisen Operatoren, die in der Programmiersprache f# verfügbar sind.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="cc398-103">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="cc398-103">Bitwise Operators</span></span>

<span data-ttu-id="cc398-104">In diesem Thema wird beschrieben, bitweise Operatoren, die in der Programmiersprache f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cc398-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="cc398-105">Zusammenfassung der bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="cc398-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="cc398-106">Die folgende Tabelle beschreibt die bitweisen Operatoren, die für nicht geschachtelte ganzzahlige Typen in der Programmiersprache f# unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cc398-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="cc398-107">Operator</span><span class="sxs-lookup"><span data-stu-id="cc398-107">Operator</span></span>|<span data-ttu-id="cc398-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc398-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="cc398-109">Bitweiser AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-109">Bitwise AND operator.</span></span> <span data-ttu-id="cc398-110">Bits im Resultset haben den Wert 1, wenn die entsprechenden Bits in beide Quelloperanden den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="cc398-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="cc398-111">Bitweiser OR-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-111">Bitwise OR operator.</span></span> <span data-ttu-id="cc398-112">Bits im Resultset den Wert 1 aufweisen, wenn entweder der entsprechenden Bits in der Quelle Operanden 1 sind.</span><span class="sxs-lookup"><span data-stu-id="cc398-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="cc398-113">Bitweiser exklusiver OR-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="cc398-114">Bits im Resultset aufweisen den Wert 1, wenn Bits in den Quelloperanden ungleiche Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cc398-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="cc398-115">Bitweise Negation-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-115">Bitwise negation operator.</span></span> <span data-ttu-id="cc398-116">Dies ist ein unäroperator und erzeugt ein Ergebnis in dem alle 0 Bits in der Quelle Operand um 1 Bit konvertiert werden, und alle 1 Bit auf 0 Bits konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="cc398-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="cc398-117">Bitweiser Left Shift-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="cc398-118">Das Ergebnis ist, dass es sich bei der erste Operanden mit Bits nach links verschoben, durch die Anzahl der Bits im zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="cc398-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="cc398-119">Verschobene Position des höchstwertigen Bits werden nicht in die unwichtigsten Position gedreht.</span><span class="sxs-lookup"><span data-stu-id="cc398-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="cc398-120">Die am niedrigstwertigen Bits werden mit Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cc398-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="cc398-121">Der Typ des zweiten Arguments ist `int32`.</span><span class="sxs-lookup"><span data-stu-id="cc398-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="cc398-122">Bitweise Rechtsschiebe-Operator.</span><span class="sxs-lookup"><span data-stu-id="cc398-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="cc398-123">Das Ergebnis ist der erste Operand mit Bits nach rechts verschoben, um die Anzahl der Bits im zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="cc398-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="cc398-124">Bits die unwichtigsten Position verschoben werden nicht in die Position des höchstwertigen gedreht.</span><span class="sxs-lookup"><span data-stu-id="cc398-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="cc398-125">Für Typen ohne Vorzeichen werden die höchstwertigen Bits mit Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cc398-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="cc398-126">Die höchstwertigen Bits werden für Typen mit Vorzeichen mit denen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cc398-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="cc398-127">Der Typ des zweiten Arguments ist `int32`.</span><span class="sxs-lookup"><span data-stu-id="cc398-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="cc398-128">Die folgenden Typen können mit bitweisen Operatoren verwendet werden: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, und `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="cc398-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc398-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc398-129">See Also</span></span>
[<span data-ttu-id="cc398-130">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="cc398-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="cc398-131">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="cc398-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="cc398-132">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="cc398-132">Boolean Operators</span></span>](boolean-operators.md)

