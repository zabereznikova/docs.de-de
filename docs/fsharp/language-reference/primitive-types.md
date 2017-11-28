---
title: Primitive Typen (F#)
description: Ermitteln Sie die grundlegenden primitiven Typen, die in der Programmiersprache f# verwendet werden.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f23d98b-551b-4fd2-9f4f-0fd7254288ed
ms.openlocfilehash: b493cdf7116d94f66940d03b86e584bcecbbb0f1
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="primitive-types"></a><span data-ttu-id="91e84-104">Primitive Typen</span><span class="sxs-lookup"><span data-stu-id="91e84-104">Primitive Types</span></span>

<span data-ttu-id="91e84-105">Dieses Thema enthält die grundlegenden primitiven Typen, die in der Programmiersprache f# verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91e84-105">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="91e84-106">Darüber hinaus werden die entsprechenden Typen in .NET und die minimalen und maximalen Werte für jeden Typ bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="91e84-106">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="91e84-107">Zusammenfassung der primitiven Typen</span><span class="sxs-lookup"><span data-stu-id="91e84-107">Summary of Primitive Types</span></span>
<span data-ttu-id="91e84-108">In der folgenden Tabelle werden die Eigenschaften von primitiven f#-Typen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="91e84-108">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="91e84-109">Typ</span><span class="sxs-lookup"><span data-stu-id="91e84-109">Type</span></span>|<span data-ttu-id="91e84-110">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="91e84-110">.NET type</span></span>|<span data-ttu-id="91e84-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91e84-111">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="91e84-112">Mögliche Werte sind `true` und `false`.</span><span class="sxs-lookup"><span data-stu-id="91e84-112">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="91e84-113">Werte von 0 bis 255.</span><span class="sxs-lookup"><span data-stu-id="91e84-113">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="91e84-114">Werte von-128 bis 127.</span><span class="sxs-lookup"><span data-stu-id="91e84-114">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="91e84-115">Werte von-32768 bis 32767.</span><span class="sxs-lookup"><span data-stu-id="91e84-115">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="91e84-116">Werte von 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="91e84-116">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="91e84-117">Werte von -2.147.483.648 bis 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="91e84-117">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="91e84-118">Werte zwischen 0 und 4.294.967.295 ein.</span><span class="sxs-lookup"><span data-stu-id="91e84-118">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="91e84-119">Werte von -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="91e84-119">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="91e84-120">Werte von 0 bis 18.446.744.073.709.551.615.</span><span class="sxs-lookup"><span data-stu-id="91e84-120">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="91e84-121">Ein systemeigener Zeiger als eine Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="91e84-121">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="91e84-122">Ein systemeigener Zeiger als ganze Zahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="91e84-122">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="91e84-123">Unicode-Zeichenwerte.</span><span class="sxs-lookup"><span data-stu-id="91e84-123">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="91e84-124">Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="91e84-124">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="91e84-125">Ein Gleitkommawert-Datentyp, der mindestens 28 signifikante Ziffern umfasst.</span><span class="sxs-lookup"><span data-stu-id="91e84-125">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="91e84-126">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="91e84-126">not applicable</span></span>|<span data-ttu-id="91e84-127">Gibt das Fehlen eines tatsächlichen Werts.</span><span class="sxs-lookup"><span data-stu-id="91e84-127">Indicates the absence of an actual value.</span></span> <span data-ttu-id="91e84-128">Der Typ hat nur einen formalen Wert ab, die gekennzeichnet ist `()`.</span><span class="sxs-lookup"><span data-stu-id="91e84-128">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="91e84-129">Den Einheitswert `()`, wird häufig als Platzhalter, in dem ein Wert benötigt wird, aber keine echten Wert verfügbar ist oder sinnvoll, verwendet.</span><span class="sxs-lookup"><span data-stu-id="91e84-129">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="91e84-130">Gibt an, kein Typ oder Wert.</span><span class="sxs-lookup"><span data-stu-id="91e84-130">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="91e84-131">Eine 32-Bit-Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="91e84-131">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="91e84-132">Eine 64-Bit-Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="91e84-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="91e84-133">Sie können Berechnungen mit ganzen Zahlen zu groß für den 64-Bit-Ganzzahl-Typ ausführen, mit der ["bigint"](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) Typ.</span><span class="sxs-lookup"><span data-stu-id="91e84-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="91e84-134">`bigint`einen primitiven Typ ist nicht berücksichtigt werden; Es ist eine Abkürzung für `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="91e84-134">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="91e84-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91e84-135">See Also</span></span>
[<span data-ttu-id="91e84-136">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="91e84-136">F# Language Reference</span></span>](index.md)
