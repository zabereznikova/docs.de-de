---
title: Grundlegende Typen (f#)
description: Entdecken Sie die grundlegenden, einfachen Typen, die in der Sprache f# verwendet werden.
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44202205"
---
# <a name="basic-types"></a><span data-ttu-id="fb3ee-103">Grundlegende Typen</span><span class="sxs-lookup"><span data-stu-id="fb3ee-103">Basic types</span></span>

<span data-ttu-id="fb3ee-104">Dieses Thema enthält die grundlegenden Typen, die in der F#-Sprache definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="fb3ee-105">Diese Typen sind der wichtigste in f#, bilden die Grundlage für fast jede f#-Programm.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="fb3ee-106">Sie sind eine Obermenge von primitiven .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="fb3ee-107">Typ</span><span class="sxs-lookup"><span data-stu-id="fb3ee-107">Type</span></span>|<span data-ttu-id="fb3ee-108">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="fb3ee-108">.NET type</span></span>|<span data-ttu-id="fb3ee-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb3ee-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="fb3ee-110">Mögliche Werte sind `true` und `false`.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="fb3ee-111">Die Werte von 0 bis 255.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="fb3ee-112">Werte von-128 bis 127.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="fb3ee-113">Werte von-32768 bis 32767.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="fb3ee-114">Werte von 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="fb3ee-115">Die Werte von-2.147.483.648 bis 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="fb3ee-116">Die Werte von 0 bis 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="fb3ee-117">Die Werte von-9.223.372.036.854.775.808 bis + 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="fb3ee-118">Werte von 0 bis 18.446.744.073.709.551.615.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="fb3ee-119">Ein systemeigener Zeiger als eine Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="fb3ee-120">Ein systemeigener Zeiger als ganze Zahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="fb3ee-121">Unicode-Zeichenwerte.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="fb3ee-122">Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="fb3ee-123">Ein Gleitkommawert-Datentyp, der mindestens 28 signifikante Ziffern umfasst.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="fb3ee-124">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="fb3ee-124">not applicable</span></span>|<span data-ttu-id="fb3ee-125">Gibt das Fehlen eines tatsächlichen Werts.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="fb3ee-126">Der Typ aufweist, nur eine formale Wert, der gekennzeichnet ist `()`.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="fb3ee-127">Der Einheitenwert `()`, dient häufig als Platzhalter, in dem ein Wert erforderlich ist, aber keine echter Wert verfügbar ist oder sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="fb3ee-128">Gibt an, kein Typ oder Wert.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="fb3ee-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="fb3ee-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="fb3ee-130">Eine 32-Bit-Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="fb3ee-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="fb3ee-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="fb3ee-132">Eine 64-Bit-Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="fb3ee-133">Sie können Berechnungen mit ganzen Zahlen zu groß für den 64-Bit-Ganzzahl-Typ ausführen, indem Sie mit der [Bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) Typ.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="fb3ee-134">`bigint` ein Basistyp wurde nicht betrachtet werden. Es ist eine Abkürzung für `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="fb3ee-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb3ee-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb3ee-135">See also</span></span>

- [<span data-ttu-id="fb3ee-136">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fb3ee-136">F# Language Reference</span></span>](index.md)
