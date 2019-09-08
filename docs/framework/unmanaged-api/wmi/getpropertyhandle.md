---
title: Getpropertyhandle-Funktion (Referenz zur nicht verwalteten API)
description: Die getpropertyhandle-Funktion gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.
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
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798539"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="8b32c-103">GetPropertyHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="8b32c-103">GetPropertyHandle function</span></span>

<span data-ttu-id="8b32c-104">Gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8b32c-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8b32c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b32c-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="8b32c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b32c-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="8b32c-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b32c-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="8b32c-108">in Ein Zeiger auf eine [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="8b32c-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="8b32c-109">in Eine NULL-terminierte Zeichenfolge von UTF16-codierten Zeichen, die den Eigenschaftsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="8b32c-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="8b32c-110">vorgenommen Ein Zeiger auf einen [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) -Enumerationsmember, der den CIM-Typ der Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b32c-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="8b32c-111">vorgenommen Ein Zeiger auf eine ganze Zahl, die das Eigenschaften Handle enthält.</span><span class="sxs-lookup"><span data-stu-id="8b32c-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="8b32c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b32c-112">Return value</span></span>

<span data-ttu-id="8b32c-113">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="8b32c-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8b32c-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="8b32c-114">Constant</span></span>  |<span data-ttu-id="8b32c-115">Wert</span><span class="sxs-lookup"><span data-stu-id="8b32c-115">Value</span></span>  |<span data-ttu-id="8b32c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b32c-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8b32c-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8b32c-117">0x80041002</span></span> | <span data-ttu-id="8b32c-118">Der angegebene Eigenschaften Name wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8b32c-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8b32c-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8b32c-119">0x80041008</span></span> | <span data-ttu-id="8b32c-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8b32c-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="8b32c-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="8b32c-121">0x8004100c</span></span> | <span data-ttu-id="8b32c-122">Die angeforderte Eigenschaft ist vom `CIM_OBJECT` Datentyp `CIM_ARRAY`oder.</span><span class="sxs-lookup"><span data-stu-id="8b32c-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8b32c-123">0</span><span class="sxs-lookup"><span data-stu-id="8b32c-123">0</span></span> | <span data-ttu-id="8b32c-124">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8b32c-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="8b32c-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b32c-125">Remarks</span></span>

<span data-ttu-id="8b32c-126">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: getpropertyhandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8b32c-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="8b32c-127">Sie können dieses Handle verwenden, um Eigenschaften zu identifizieren, wenn Sie die [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Methoden zum Lesen oder Schreiben von Eigenschafts Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b32c-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="8b32c-128">Handles können für Eigenschaften aller anderen Datentypen als `CIM_OBJECT` und `CIM_ARRAY`abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8b32c-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="8b32c-129">Zurückgegebene Handles funktionieren in allen Instanzen einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="8b32c-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b32c-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b32c-130">Requirements</span></span>

<span data-ttu-id="8b32c-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b32c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8b32c-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8b32c-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="8b32c-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b32c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8b32c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b32c-134">See also</span></span>

- [<span data-ttu-id="8b32c-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8b32c-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
