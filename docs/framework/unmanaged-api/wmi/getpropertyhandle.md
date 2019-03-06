---
title: GetPropertyHandle-Funktion (Referenz zur nicht verwalteten API)
description: GetPropertyHandle-Funktion gibt ein eindeutige Handle, das eine Eigenschaft identifiziert.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92d48caf7de873850135c7410a5e4b5861131212
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366373"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="2d7d7-103">GetPropertyHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d7d7-103">GetPropertyHandle function</span></span>

<span data-ttu-id="2d7d7-104">Gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="2d7d7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d7d7-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="2d7d7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d7d7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="2d7d7-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="2d7d7-108">[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="2d7d7-109">[in] Eine Null-terminierte Zeichenfolge des UTF16-codierte Zeichen, die den Eigenschaftennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="2d7d7-110">[out] Ein Zeiger auf eine [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) -Enumerationsmember, der den CIM-Typ der Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-110">[out] A pointer to a [`CIMTYPE`](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="2d7d7-111">[out] Ein Zeiger auf eine ganze Zahl, die das Eigenschaftshandle enthält.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="2d7d7-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d7d7-112">Return value</span></span>

<span data-ttu-id="2d7d7-113">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="2d7d7-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2d7d7-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="2d7d7-114">Constant</span></span>  |<span data-ttu-id="2d7d7-115">Wert</span><span class="sxs-lookup"><span data-stu-id="2d7d7-115">Value</span></span>  |<span data-ttu-id="2d7d7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d7d7-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="2d7d7-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="2d7d7-117">0x80041002</span></span> | <span data-ttu-id="2d7d7-118">Der angegebene Eigenschaftenname wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2d7d7-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2d7d7-119">0x80041008</span></span> | <span data-ttu-id="2d7d7-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="2d7d7-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="2d7d7-121">0x8004100c</span></span> | <span data-ttu-id="2d7d7-122">Die angeforderte Eigenschaft ist vom Typ sind `CIM_OBJECT` oder `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2d7d7-123">0</span><span class="sxs-lookup"><span data-stu-id="2d7d7-123">0</span></span> | <span data-ttu-id="2d7d7-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="2d7d7-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d7d7-125">Remarks</span></span>

<span data-ttu-id="2d7d7-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) Methode.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="2d7d7-127">Sie können dieses Handle verwenden, um Eigenschaften zu identifizieren, bei Verwendung [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Methoden zum Lesen oder Schreiben von Eigenschaftswerten.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="2d7d7-128">Handles können nicht für die Eigenschaften aller Datentypen abgerufen werden `CIM_OBJECT` und `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="2d7d7-129">Handles Arbeit, die über alle Instanzen einer Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d7d7-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d7d7-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d7d7-130">Requirements</span></span>

<span data-ttu-id="2d7d7-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2d7d7-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2d7d7-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="2d7d7-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d7d7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2d7d7-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d7d7-134">See also</span></span>

- [<span data-ttu-id="2d7d7-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2d7d7-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)