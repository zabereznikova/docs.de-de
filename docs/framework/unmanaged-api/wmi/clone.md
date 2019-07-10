---
title: Clone-Funktion (Referenz zur nicht verwalteten API)
description: Die Klon-Funktion gibt es sich um ein neues Objekt, das einen Klon der aktuellen Aktivität abgeschlossen ist.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80faf1a5a6297f5b105fdb609366f6774f8692b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761647"
---
# <a name="clone-function"></a><span data-ttu-id="20a78-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="20a78-103">Clone function</span></span>
<span data-ttu-id="20a78-104">Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="20a78-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="20a78-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="20a78-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="20a78-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="20a78-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="20a78-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="20a78-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="20a78-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="20a78-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="20a78-109">[out] Ein neues Objekt, das eine vollständige ist der einzelne `ptr`.</span><span class="sxs-lookup"><span data-stu-id="20a78-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="20a78-110">Dieses Argument nicht `null` empfängt er die Kopie des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="20a78-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="20a78-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20a78-111">Return value</span></span>

<span data-ttu-id="20a78-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="20a78-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20a78-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="20a78-113">Constant</span></span>  |<span data-ttu-id="20a78-114">Wert</span><span class="sxs-lookup"><span data-stu-id="20a78-114">Value</span></span>  |<span data-ttu-id="20a78-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20a78-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="20a78-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="20a78-116">0x80041001</span></span> | <span data-ttu-id="20a78-117">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="20a78-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="20a78-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="20a78-118">0x80041008</span></span> | <span data-ttu-id="20a78-119">`null` als Parameter angegeben wurde, und es ist nicht zulässig, bei dieser Verwendung.</span><span class="sxs-lookup"><span data-stu-id="20a78-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="20a78-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="20a78-120">0x80041006</span></span> | <span data-ttu-id="20a78-121">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um das Objekt zu klonen.</span><span class="sxs-lookup"><span data-stu-id="20a78-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="20a78-122">0</span><span class="sxs-lookup"><span data-stu-id="20a78-122">0</span></span> | <span data-ttu-id="20a78-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="20a78-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="20a78-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20a78-124">Remarks</span></span>

<span data-ttu-id="20a78-125">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="20a78-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="20a78-126">Das geklonte Objekt ist ein COM-Objekt mit einer Verweisanzahl von 1.</span><span class="sxs-lookup"><span data-stu-id="20a78-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="20a78-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20a78-127">Requirements</span></span>  
 <span data-ttu-id="20a78-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20a78-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20a78-129">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="20a78-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="20a78-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20a78-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a78-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20a78-131">See also</span></span>

- [<span data-ttu-id="20a78-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="20a78-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
