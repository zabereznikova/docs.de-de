---
title: CorElementType-Enumeration
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
ms.openlocfilehash: 6057bd48ff4fe3f852f82de2bab972d95fef138c
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868565"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="6b70d-102">CorElementType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6b70d-102">CorElementType Enumeration</span></span>

<span data-ttu-id="6b70d-103">Gibt eine Common Language Runtime <xref:System.Type>, einen Typmodifizierer oder Informationen zu einem Typ in einer Signatur des metadatentyps an.</span><span class="sxs-lookup"><span data-stu-id="6b70d-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b70d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b70d-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="6b70d-105">Member</span><span class="sxs-lookup"><span data-stu-id="6b70d-105">Members</span></span>

|<span data-ttu-id="6b70d-106">Member</span><span class="sxs-lookup"><span data-stu-id="6b70d-106">Member</span></span>|<span data-ttu-id="6b70d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b70d-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="6b70d-108">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b70d-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="6b70d-109">Ein void-Typ.</span><span class="sxs-lookup"><span data-stu-id="6b70d-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="6b70d-110">Ein boolescher Typ</span><span class="sxs-lookup"><span data-stu-id="6b70d-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="6b70d-111">Ein Zeichentyp.</span><span class="sxs-lookup"><span data-stu-id="6b70d-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="6b70d-112">Eine ganze 1-Byte-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="6b70d-113">Ein unsignierter 1-Byte-Ganzzahltyp.</span><span class="sxs-lookup"><span data-stu-id="6b70d-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="6b70d-114">Eine ganze 2-Byte-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="6b70d-115">Eine 2-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="6b70d-116">Eine ganze 4-Byte-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="6b70d-117">Eine ganze 4-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="6b70d-118">Eine 8-Byte-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="6b70d-119">Eine 8-Byte-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="6b70d-120">Ein 4-Byte-Gleit Komma Wert.</span><span class="sxs-lookup"><span data-stu-id="6b70d-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="6b70d-121">Ein 8-Byte-Gleit Komma Wert.</span><span class="sxs-lookup"><span data-stu-id="6b70d-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="6b70d-122">Ein System. String-Typ.</span><span class="sxs-lookup"><span data-stu-id="6b70d-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="6b70d-123">Ein zeigertypmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="6b70d-124">Ein Verweistyp Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="6b70d-125">Ein Werttyp-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="6b70d-126">Ein Klassentyp Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="6b70d-127">Ein Klassen variablentypmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="6b70d-128">Ein mehrdimensionaler Arraytypmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="6b70d-129">Ein Typmodifizierer für generische Typen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="6b70d-130">Ein typisierter Verweis.</span><span class="sxs-lookup"><span data-stu-id="6b70d-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="6b70d-131">Größe einer nativen Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="6b70d-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="6b70d-132">Größe einer nativen Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="6b70d-133">Ein Zeiger auf eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="6b70d-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="6b70d-134">Ein System. Object-Typ.</span><span class="sxs-lookup"><span data-stu-id="6b70d-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="6b70d-135">Ein eindimensionaler Arraytypmodifizierer (null).</span><span class="sxs-lookup"><span data-stu-id="6b70d-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="6b70d-136">Ein Typmodifizierer für die-Methode.</span><span class="sxs-lookup"><span data-stu-id="6b70d-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="6b70d-137">Ein Modifizierer der C-Sprache erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b70d-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="6b70d-138">Ein optionaler C-sprach Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="6b70d-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="6b70d-139">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b70d-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="6b70d-140">Ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="6b70d-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="6b70d-141">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b70d-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="6b70d-142">Ein Typmodifizierer, bei dem es sich um einen Sentinel für eine Liste mit einer Variablen Anzahl von Parametern handelt.</span><span class="sxs-lookup"><span data-stu-id="6b70d-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="6b70d-143">Wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b70d-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6b70d-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b70d-144">Remarks</span></span>

<span data-ttu-id="6b70d-145">Die typmodifiziererer bilden die Grundlage für das darstellen komplexer Typen.</span><span class="sxs-lookup"><span data-stu-id="6b70d-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="6b70d-146">Ein `CorElementType` Typmodifiziererwert wird auf den Wert angewendet, der in der Typsignatur unmittelbar darauf folgt.</span><span class="sxs-lookup"><span data-stu-id="6b70d-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="6b70d-147">Der Wert, der auf `CorElementType` den Typmodifiziererwert folgt `CorElementType` , kann ein einfacher Typwert, ein Metadatentoken oder ein anderer Wert sein, wie in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="6b70d-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="6b70d-148">Alle Zahlen (*Anzahl*, *Argument Anzahl*,Metadatentoken, *Rang*, *Anzahl*und *gebunden*) werden als komprimierte ganze Zahlen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6b70d-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="6b70d-149">Weitere Informationen finden Sie in der ECMA [-Website Standard-ECMA-335-Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) .</span><span class="sxs-lookup"><span data-stu-id="6b70d-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="6b70d-150">Typmodifizierer</span><span class="sxs-lookup"><span data-stu-id="6b70d-150">Type modifier</span></span>|<span data-ttu-id="6b70d-151">Format</span><span class="sxs-lookup"><span data-stu-id="6b70d-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="6b70d-152">ELEMENT_TYPE_PTR \< ein`CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="6b70d-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="6b70d-153">ELEMENT_TYPE_BYREF \< ein`CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="6b70d-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="6b70d-154">ELEMENT_TYPE_VALUETYPE \< ein`mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="6b70d-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="6b70d-155">ELEMENT_TYPE_CLASS \< ein`mdTypeDef` Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="6b70d-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="6b70d-156">ELEMENT_TYPE_VAR \<Anzahl ></span><span class="sxs-lookup"><span data-stu-id="6b70d-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="6b70d-157">ELEMENT_TYPE_ARRAY \<ein `CorElementType` Wert > \<Rang > \<count1 >\<bound1 >... \< >\<boundn ></span><span class="sxs-lookup"><span data-stu-id="6b70d-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="6b70d-158">ELEMENT_TYPE_GENERICINST \< \< \<ein `mdTypeDef` Metadatentoken > Argument Anzahl > arg1 >... \<argN-></span><span class="sxs-lookup"><span data-stu-id="6b70d-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="6b70d-159">ELEMENT_TYPE_FNPTR \<vervollständigen der Signatur für die Funktion, einschließlich der Aufruf Konvention ></span><span class="sxs-lookup"><span data-stu-id="6b70d-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="6b70d-160">ELEMENT_TYPE_SZARRAY \< ein`CorElementType` Wert ></span><span class="sxs-lookup"><span data-stu-id="6b70d-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="6b70d-161">ELEMENT_TYPE_MVAR \<Anzahl ></span><span class="sxs-lookup"><span data-stu-id="6b70d-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="6b70d-162">ELEMENT_TYPE_\<ein `mdTypeRef` - oder`mdTypeDef` -Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="6b70d-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="6b70d-163">E_T_CMOD_OPT \<ein `mdTypeRef` - oder`mdTypeDef` -Metadatentoken ></span><span class="sxs-lookup"><span data-stu-id="6b70d-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="6b70d-164">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b70d-164">Requirements</span></span>

<span data-ttu-id="6b70d-165">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b70d-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6b70d-166">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6b70d-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="6b70d-167">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b70d-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6b70d-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b70d-168">See also</span></span>

- [<span data-ttu-id="6b70d-169">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6b70d-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
