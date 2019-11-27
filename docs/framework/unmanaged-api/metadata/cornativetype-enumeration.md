---
title: CorNativeType-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: ef4788891e91608a394482319a89b8b0d258449f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436511"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="fba9e-102">CorNativeType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fba9e-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="fba9e-103">Enthält Werte, die systemeigene, nicht verwaltete Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fba9e-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fba9e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="fba9e-105">Member</span><span class="sxs-lookup"><span data-stu-id="fba9e-105">Members</span></span>  
  
|<span data-ttu-id="fba9e-106">Member</span><span class="sxs-lookup"><span data-stu-id="fba9e-106">Member</span></span>|<span data-ttu-id="fba9e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fba9e-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="fba9e-108">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="fba9e-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="fba9e-110">Ein boolescher Wert mit 4 Byte, wobei TRUE ungleich NULL und false NULL ist.</span><span class="sxs-lookup"><span data-stu-id="fba9e-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="fba9e-111">Ein 8-Bit-ganzzahliger Wert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="fba9e-112">Ein 8-Bit-ganzzahliger Wert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="fba9e-113">Ein 16-Bit-ganzzahliger Wert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="fba9e-114">Ein 16-Bit-Ganzzahl-Wert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="fba9e-115">Ein 32-Bit-Ganzzahlwert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="fba9e-116">Ein 32-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="fba9e-117">Ein ganzzahliger 64-Bit-Wert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="fba9e-118">Ein ganzzahliger 64-Bit-Wert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="fba9e-119">Ein numerischer 4-Byte-Gleit Komma Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="fba9e-120">Ein numerischer 8-Byte-Gleit Komma Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="fba9e-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="fba9e-122">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="fba9e-123">Ein numerischer COM-Typ, der dem verwalteten <xref:System.Decimal>-Typ entspricht.</span><span class="sxs-lookup"><span data-stu-id="fba9e-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="fba9e-124">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="fba9e-125">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="fba9e-126">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="fba9e-127">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="fba9e-128">Ein LPSTR-Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="fba9e-129">Ein LPWSTR-Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="fba9e-130">Ein LPTSTR-Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="fba9e-131">Ein fester, System definierter Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="fba9e-132">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="fba9e-133">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="fba9e-134">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="fba9e-135">Ein nativer Struktur Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="fba9e-136">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="fba9e-137">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="fba9e-138">Ein Array Wert mit fester Länge.</span><span class="sxs-lookup"><span data-stu-id="fba9e-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="fba9e-139">Ein nativer ganzzahliger 16-Bit-Wert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="fba9e-140">Ein nativer 16-Bit-Ganzzahl-Wert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="fba9e-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="fba9e-141">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="fba9e-142">Verwenden Sie NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="fba9e-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="fba9e-143">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="fba9e-144">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="fba9e-145">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="fba9e-146">Wählen Sie je nach Plattform BSTR oder ANSIBSTR aus.</span><span class="sxs-lookup"><span data-stu-id="fba9e-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="fba9e-147">Ein boolescher 2-Byte-Wert, wobei true-1 und false 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="fba9e-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="fba9e-148">Ein Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="fba9e-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="fba9e-149">Ein Verweis auf einen beliebigen systemeigenen Typ.</span><span class="sxs-lookup"><span data-stu-id="fba9e-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="fba9e-150">Ein Verweis auf ein Array mit Membern eines nicht angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="fba9e-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="fba9e-151">Ein ganzzahliger 32-Bit-Zeiger auf eine-Struktur.</span><span class="sxs-lookup"><span data-stu-id="fba9e-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="fba9e-152">Ein benutzerdefinierter Mars Haller-Typ.</span><span class="sxs-lookup"><span data-stu-id="fba9e-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="fba9e-153">Auf diese muss eine Zeichenfolge im folgenden Format folgen: "System eigener Typname/0benutzer definierter Mars Haller-Typname/0optionales Cookie/0" oder "{Native Type GUID}/0Custom Mars Haller Type Name/0optional Cookie/0"</span><span class="sxs-lookup"><span data-stu-id="fba9e-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="fba9e-154">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="fba9e-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="fba9e-155">Bei ELEMENT_TYPE_I4 dieser Typ VT_HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fba9e-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="fba9e-156">Ein System eigener `IInspectable` Typ.</span><span class="sxs-lookup"><span data-stu-id="fba9e-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="fba9e-157">Eine systemeigene `HString`.</span><span class="sxs-lookup"><span data-stu-id="fba9e-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="fba9e-158">Ein ungültiger Wert.</span><span class="sxs-lookup"><span data-stu-id="fba9e-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fba9e-159">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fba9e-159">Requirements</span></span>  
 <span data-ttu-id="fba9e-160">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fba9e-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba9e-161">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="fba9e-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fba9e-162">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fba9e-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba9e-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fba9e-163">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="fba9e-164">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fba9e-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
