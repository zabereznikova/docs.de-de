---
title: Bitweise Operatoren (F#)
description: "Erfahren Sie, bis die bitweisen Operatoren, die in der Programmiersprache f# verfügbar sind."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a><span data-ttu-id="741e8-104">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="741e8-104">Bitwise Operators</span></span>

<span data-ttu-id="741e8-105">In diesem Thema wird beschrieben, bitweise Operatoren, die in der Programmiersprache f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="741e8-105">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="741e8-106">Zusammenfassung der bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="741e8-106">Summary of Bitwise Operators</span></span>
<span data-ttu-id="741e8-107">Die folgende Tabelle beschreibt die bitweisen Operatoren, die für nicht geschachtelte ganzzahlige Typen in der Programmiersprache f# unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="741e8-107">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="741e8-108">Operator</span><span class="sxs-lookup"><span data-stu-id="741e8-108">Operator</span></span>|<span data-ttu-id="741e8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="741e8-109">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="741e8-110">Bitweiser AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-110">Bitwise AND operator.</span></span> <span data-ttu-id="741e8-111">Bits im Resultset haben den Wert 1, wenn die entsprechenden Bits in beide Quelloperanden den Wert 1 haben.</span><span class="sxs-lookup"><span data-stu-id="741e8-111">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="741e8-112">Bitweiser OR-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-112">Bitwise OR operator.</span></span> <span data-ttu-id="741e8-113">Bits im Resultset den Wert 1 aufweisen, wenn entweder der entsprechenden Bits in der Quelle Operanden 1 sind.</span><span class="sxs-lookup"><span data-stu-id="741e8-113">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="741e8-114">Bitweiser exklusiver OR-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-114">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="741e8-115">Bits im Resultset aufweisen den Wert 1, wenn Bits in den Quelloperanden ungleiche Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="741e8-115">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="741e8-116">Bitweise Negation-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-116">Bitwise negation operator.</span></span> <span data-ttu-id="741e8-117">Dies ist ein unäroperator und erzeugt ein Ergebnis in dem alle 0 Bits in der Quelle Operand um 1 Bit konvertiert werden, und alle 1 Bit auf 0 Bits konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="741e8-117">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="741e8-118">Bitweiser Left Shift-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-118">Bitwise left-shift operator.</span></span> <span data-ttu-id="741e8-119">Das Ergebnis ist, dass es sich bei der erste Operanden mit Bits nach links verschoben, durch die Anzahl der Bits im zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="741e8-119">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="741e8-120">Verschobene Position des höchstwertigen Bits werden nicht in die unwichtigsten Position gedreht.</span><span class="sxs-lookup"><span data-stu-id="741e8-120">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="741e8-121">Die am niedrigstwertigen Bits werden mit Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="741e8-121">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="741e8-122">Der Typ des zweiten Arguments ist `int32`.</span><span class="sxs-lookup"><span data-stu-id="741e8-122">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="741e8-123">Bitweise Rechtsschiebe-Operator.</span><span class="sxs-lookup"><span data-stu-id="741e8-123">Bitwise right-shift operator.</span></span> <span data-ttu-id="741e8-124">Das Ergebnis ist der erste Operand mit Bits nach rechts verschoben, um die Anzahl der Bits im zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="741e8-124">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="741e8-125">Bits die unwichtigsten Position verschoben werden nicht in die Position des höchstwertigen gedreht.</span><span class="sxs-lookup"><span data-stu-id="741e8-125">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="741e8-126">Für Typen ohne Vorzeichen werden die höchstwertigen Bits mit Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="741e8-126">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="741e8-127">Die höchstwertigen Bits werden für Typen mit Vorzeichen mit denen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="741e8-127">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="741e8-128">Der Typ des zweiten Arguments ist `int32`.</span><span class="sxs-lookup"><span data-stu-id="741e8-128">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="741e8-129">Die folgenden Typen können mit bitweisen Operatoren verwendet werden: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, und `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="741e8-129">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="741e8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="741e8-130">See Also</span></span>
[<span data-ttu-id="741e8-131">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="741e8-131">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="741e8-132">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="741e8-132">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="741e8-133">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="741e8-133">Boolean Operators</span></span>](boolean-operators.md)

