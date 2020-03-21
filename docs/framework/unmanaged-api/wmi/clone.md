---
title: Klonfunktion (Nicht verwaltete API-Referenz)
description: Die Clone-Funktion gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176850"
---
# <a name="clone-function"></a><span data-ttu-id="430c1-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="430c1-103">Clone function</span></span>
<span data-ttu-id="430c1-104">Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="430c1-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="430c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="430c1-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="430c1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="430c1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="430c1-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="430c1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="430c1-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="430c1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="430c1-109">[out] Ein neues Objekt, das vollständig `ptr`einsam von ist.</span><span class="sxs-lookup"><span data-stu-id="430c1-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="430c1-110">Dieses Argument `null` kann nicht sein, wenn es die Kopie des aktuellen Objekts empfängt.</span><span class="sxs-lookup"><span data-stu-id="430c1-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="430c1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="430c1-111">Return value</span></span>

<span data-ttu-id="430c1-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="430c1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="430c1-113">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="430c1-113">Constant</span></span>  |<span data-ttu-id="430c1-114">value</span><span class="sxs-lookup"><span data-stu-id="430c1-114">Value</span></span>  |<span data-ttu-id="430c1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="430c1-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="430c1-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="430c1-116">0x80041001</span></span> | <span data-ttu-id="430c1-117">Es ist ein allgemeines Versagen aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="430c1-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="430c1-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="430c1-118">0x80041008</span></span> | <span data-ttu-id="430c1-119">`null`wurde als Parameter angegeben, und es ist in dieser Verwendung nicht legal.</span><span class="sxs-lookup"><span data-stu-id="430c1-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="430c1-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="430c1-120">0x80041006</span></span> | <span data-ttu-id="430c1-121">Es ist nicht genügend Arbeitsspeicher verfügbar, um das Objekt zu klonen.</span><span class="sxs-lookup"><span data-stu-id="430c1-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="430c1-122">0</span><span class="sxs-lookup"><span data-stu-id="430c1-122">0</span></span> | <span data-ttu-id="430c1-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="430c1-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="430c1-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="430c1-124">Remarks</span></span>

<span data-ttu-id="430c1-125">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Clone-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="430c1-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="430c1-126">Das geklonte Objekt ist ein COM-Objekt mit einer Referenzanzahl von 1.</span><span class="sxs-lookup"><span data-stu-id="430c1-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="430c1-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="430c1-127">Requirements</span></span>  
 <span data-ttu-id="430c1-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="430c1-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="430c1-129">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="430c1-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="430c1-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="430c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430c1-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="430c1-131">See also</span></span>

- [<span data-ttu-id="430c1-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="430c1-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
