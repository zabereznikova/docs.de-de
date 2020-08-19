---
title: Grundlegende Typen
description: 'Entdecken Sie die grundlegenden Typen, die in der Sprache F # verwendet werden.'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557697"
---
# <a name="basic-types"></a><span data-ttu-id="74417-103">Grundlegende Typen</span><span class="sxs-lookup"><span data-stu-id="74417-103">Basic types</span></span>

<span data-ttu-id="74417-104">In diesem Thema werden die grundlegenden Typen aufgeführt, die in der Sprache F # definiert sind.</span><span class="sxs-lookup"><span data-stu-id="74417-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="74417-105">Diese Typen sind die grundlegendsten in f # und bilden die Grundlage für fast alle f #-Programme.</span><span class="sxs-lookup"><span data-stu-id="74417-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="74417-106">Dabei handelt es sich um eine supermenge von primitiven .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="74417-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="74417-107">type</span><span class="sxs-lookup"><span data-stu-id="74417-107">Type</span></span>|<span data-ttu-id="74417-108">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="74417-108">.NET type</span></span>|<span data-ttu-id="74417-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74417-109">Description</span></span>|<span data-ttu-id="74417-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74417-110">Example</span></span>|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="74417-111">Mögliche Werte sind `true` und `false`.</span><span class="sxs-lookup"><span data-stu-id="74417-111">Possible values are `true` and `false`.</span></span>|`true`/`false`|
|`byte`|<xref:System.Byte>|<span data-ttu-id="74417-112">Werte zwischen 0 und 255.</span><span class="sxs-lookup"><span data-stu-id="74417-112">Values from 0 to 255.</span></span>|`1uy`|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="74417-113">Werte von-128 bis 127.</span><span class="sxs-lookup"><span data-stu-id="74417-113">Values from -128 to 127.</span></span>|`1y`|
|`int16`|<xref:System.Int16>|<span data-ttu-id="74417-114">Werte von-32768 bis 32767.</span><span class="sxs-lookup"><span data-stu-id="74417-114">Values from -32768 to 32767.</span></span>|`1s`|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="74417-115">Werte zwischen 0 und 65535.</span><span class="sxs-lookup"><span data-stu-id="74417-115">Values from 0 to 65535.</span></span>|`1us`|
|`int`|<xref:System.Int32>|<span data-ttu-id="74417-116">Werte von-2.147.483.648 bis 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="74417-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|`1`|
|`uint`|<xref:System.UInt32>|<span data-ttu-id="74417-117">Werte zwischen 0 und 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="74417-117">Values from 0 to 4,294,967,295.</span></span>|`1u`|
|`int64`|<xref:System.Int64>|<span data-ttu-id="74417-118">Werte von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="74417-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|`1L`|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="74417-119">Werte zwischen 0 und 18446744073709551615.</span><span class="sxs-lookup"><span data-stu-id="74417-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|`1UL`|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="74417-120">Ein nativer Zeiger als Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="74417-120">A native pointer as a signed integer.</span></span>|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="74417-121">Ein nativer Zeiger als ganze Zahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="74417-121">A native pointer as an unsigned integer.</span></span>|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="74417-122">Ein Gleit Komma Datentyp mit mindestens 28 signifikanten Ziffern.</span><span class="sxs-lookup"><span data-stu-id="74417-122">A floating point data type that has at least 28 significant digits.</span></span>|`1.0`|
|<span data-ttu-id="74417-123">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="74417-123">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="74417-124">Ein 64-Bit-Gleit kommatyp.</span><span class="sxs-lookup"><span data-stu-id="74417-124">A 64-bit floating point type.</span></span>|`1.0`|
|<span data-ttu-id="74417-125">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="74417-125">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="74417-126">Ein 32-Bit-Gleit kommatyp.</span><span class="sxs-lookup"><span data-stu-id="74417-126">A 32-bit floating point type.</span></span>|`1.0f`|
|`char`|<xref:System.Char>|<span data-ttu-id="74417-127">Unicode-Zeichen Werte.</span><span class="sxs-lookup"><span data-stu-id="74417-127">Unicode character values.</span></span>|`'c'`|
|`string`|<xref:System.String>|<span data-ttu-id="74417-128">Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="74417-128">Unicode text.</span></span>|`"str"`|
|`unit`|<span data-ttu-id="74417-129">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="74417-129">not applicable</span></span>|<span data-ttu-id="74417-130">Gibt an, dass kein tatsächlicher Wert vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="74417-130">Indicates the absence of an actual value.</span></span> <span data-ttu-id="74417-131">Der-Typ verfügt nur über einen formalen Wert, der angegeben wird `()` .</span><span class="sxs-lookup"><span data-stu-id="74417-131">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="74417-132">Der Einheits Wert `()` wird häufig als Platzhalter verwendet, bei dem ein Wert benötigt wird, aber kein echter Wert verfügbar oder sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="74417-132">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|`()`|

> [!NOTE]
> <span data-ttu-id="74417-133">Sie können Berechnungen mit ganzen Zahlen für den ganzzahligen 64-Bit-Typ durchführen, indem Sie den [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) -Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="74417-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) type.</span></span> <span data-ttu-id="74417-134">`bigint` wird nicht als Basistyp betrachtet. Dies ist eine Abkürzung für `System.Numerics.BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="74417-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74417-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74417-135">See also</span></span>

- [<span data-ttu-id="74417-136">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="74417-136">F# Language Reference</span></span>](index.md)
