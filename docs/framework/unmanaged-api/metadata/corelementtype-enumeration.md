---
title: CorElementType-Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48650a85a88f36cd51adb1bbec0436fb5d75ecfb
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690370"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="03a32-102">CorElementType-Enumeration1</span><span class="sxs-lookup"><span data-stu-id="03a32-102">CorElementType Enumeration1</span></span>

<span data-ttu-id="03a32-103">Gibt an, eine common Language Runtime <xref:System.Type>, einen Typmodifizierer oder Informationen zu einem Typ in einer Signatur der Metadaten-Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="03a32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03a32-104">Syntax</span></span>

```
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a><span data-ttu-id="03a32-105">Member</span><span class="sxs-lookup"><span data-stu-id="03a32-105">Members</span></span>

|<span data-ttu-id="03a32-106">Member</span><span class="sxs-lookup"><span data-stu-id="03a32-106">Member</span></span>|<span data-ttu-id="03a32-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03a32-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="03a32-108">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a32-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="03a32-109">Ein void-Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="03a32-110">Ein boolescher Typ</span><span class="sxs-lookup"><span data-stu-id="03a32-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="03a32-111">Ein Zeichentyp.</span><span class="sxs-lookup"><span data-stu-id="03a32-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="03a32-112">Eine 1-Byte-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="03a32-113">Ein unsignierter 1-Byte-Ganzzahltyp.</span><span class="sxs-lookup"><span data-stu-id="03a32-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="03a32-114">Eine 2-Byte-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="03a32-115">Eine 2-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="03a32-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="03a32-116">Eine 4-Byte-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="03a32-117">Eine 4-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="03a32-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="03a32-118">Eine 8-Byte-Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="03a32-119">Eine 8-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="03a32-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="03a32-120">Eine 4-Byte-Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="03a32-121">Eine 8-Byte-Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="03a32-122">Ein System.String-Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="03a32-123">Ein Typmodifizierer "Zeiger".</span><span class="sxs-lookup"><span data-stu-id="03a32-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="03a32-124">Ein Modifizierer für den Verweis-Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="03a32-125">Typmodifizierer Wert.</span><span class="sxs-lookup"><span data-stu-id="03a32-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="03a32-126">Ein Typmodifizierer "Klasse".</span><span class="sxs-lookup"><span data-stu-id="03a32-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="03a32-127">Ein Variablentyp Modifizierer der Klasse.</span><span class="sxs-lookup"><span data-stu-id="03a32-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="03a32-128">Ein mehrdimensionales Array-Typ-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="03a32-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="03a32-129">Ein Typmodifizierer für generische Typen.</span><span class="sxs-lookup"><span data-stu-id="03a32-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="03a32-130">Ein typisierter Verweis.</span><span class="sxs-lookup"><span data-stu-id="03a32-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="03a32-131">Die Größe des eine systemeigene ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="03a32-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="03a32-132">Die Größe des systemeigenen Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="03a32-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="03a32-133">Ein Zeiger auf eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="03a32-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="03a32-134">Ein System.Object-Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="03a32-135">Ein eindimensionales, NULL Typmodifizierer Untergrenze Array.</span><span class="sxs-lookup"><span data-stu-id="03a32-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="03a32-136">Methodenmodifizierer Variablentyp.</span><span class="sxs-lookup"><span data-stu-id="03a32-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="03a32-137">Eine C#-Sprache erforderlich Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="03a32-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="03a32-138">Eine C#-Sprache Optionaler Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="03a32-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="03a32-139">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a32-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="03a32-140">Ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="03a32-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="03a32-141">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a32-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="03a32-142">Ein Typmodifizierer, der eine Liste der eine Variable Anzahl von Parametern Sentinel ist.</span><span class="sxs-lookup"><span data-stu-id="03a32-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="03a32-143">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a32-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="03a32-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03a32-144">Remarks</span></span>

<span data-ttu-id="03a32-145">Der Typmodifizierer bilden die Grundlage für komplexere Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="03a32-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="03a32-146">Ein `CorElementType` Typwert-Modifizierer wird angewendet, auf den Wert, der durch den sie in der Typsignatur unmittelbar folgt.</span><span class="sxs-lookup"><span data-stu-id="03a32-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="03a32-147">Der Wert, der `CorElementType` Modifizierer Typwert möglich ein `CorElementType` einfacher Werttyp, ein Metadatentoken, oder ein anderer Wert als in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="03a32-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="03a32-148">Alle Zahlen (*Anzahl*, *Argumentanzahl*, *Metadatentoken*, *Rang*, *Anzahl*, und *gebunden*) als komprimierte ganze Zahlen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="03a32-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="03a32-149">Finden Sie unter [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) auf der ECMA-Website für Details.</span><span class="sxs-lookup"><span data-stu-id="03a32-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="03a32-150">Typmodifizierer</span><span class="sxs-lookup"><span data-stu-id="03a32-150">Type modifier</span></span>|<span data-ttu-id="03a32-151">Format</span><span class="sxs-lookup"><span data-stu-id="03a32-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="03a32-152">ELEMENT_TYPE_PTR \<eine `CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="03a32-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="03a32-153">ELEMENT_TYPE_BYREF \<eine `CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="03a32-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="03a32-154">ELEMENT_TYPE_VALUETYPE \<ein `mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="03a32-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="03a32-155">ELEMENT_TYPE_CLASS \<ein `mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="03a32-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="03a32-156">ELEMENT_TYPE_VAR \<Anzahl ></span><span class="sxs-lookup"><span data-stu-id="03a32-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="03a32-157">ELEMENT_TYPE_ARRAY \<eine `CorElementType` Wert > \<Rang > \<count1 > \<bound1 >... \<CountN > \<BoundN ></span><span class="sxs-lookup"><span data-stu-id="03a32-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="03a32-158">ELEMENT_TYPE_GENERICINST \<ein `mdTypeDef` Metadatentoken > \<Argumentanzahl > \<arg1 >... \<ArgN ></span><span class="sxs-lookup"><span data-stu-id="03a32-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="03a32-159">ELEMENT_TYPE_FNPTR \<vollständige Signatur für die Funktion, einschließlich der Aufrufkonvention ></span><span class="sxs-lookup"><span data-stu-id="03a32-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="03a32-160">ELEMENT_TYPE_SZARRAY \<eine `CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="03a32-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="03a32-161">ELEMENT_TYPE_MVAR \<Anzahl ></span><span class="sxs-lookup"><span data-stu-id="03a32-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="03a32-162">ELEMENT_TYPE_\<eine `mdTypeRef` oder `mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="03a32-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="03a32-163">E_T_CMOD_OPT \<eine `mdTypeRef` oder `mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="03a32-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="03a32-164">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03a32-164">Requirements</span></span>

<span data-ttu-id="03a32-165">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03a32-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="03a32-166">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="03a32-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="03a32-167">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03a32-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="03a32-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03a32-168">See also</span></span>

- [<span data-ttu-id="03a32-169">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="03a32-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
