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
ms.openlocfilehash: bf9cca10a580af7991889de6993e931347fc27ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120957"
---
# <a name="clone-function"></a><span data-ttu-id="eab63-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="eab63-103">Clone function</span></span>
<span data-ttu-id="eab63-104">Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="eab63-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="eab63-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eab63-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="eab63-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eab63-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eab63-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="eab63-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="eab63-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="eab63-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="eab63-109">[out] Ein neues Objekt, das eine vollständige ist der einzelne `ptr`.</span><span class="sxs-lookup"><span data-stu-id="eab63-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="eab63-110">Dieses Argument nicht `null` empfängt er die Kopie des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="eab63-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="eab63-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eab63-111">Return value</span></span>

<span data-ttu-id="eab63-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="eab63-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eab63-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="eab63-113">Constant</span></span>  |<span data-ttu-id="eab63-114">Wert</span><span class="sxs-lookup"><span data-stu-id="eab63-114">Value</span></span>  |<span data-ttu-id="eab63-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eab63-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="eab63-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="eab63-116">0x80041001</span></span> | <span data-ttu-id="eab63-117">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="eab63-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eab63-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eab63-118">0x80041008</span></span> | `null` <span data-ttu-id="eab63-119">als Parameter angegeben wurde, und es ist nicht zulässig, bei dieser Verwendung.</span><span class="sxs-lookup"><span data-stu-id="eab63-119">was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="eab63-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="eab63-120">0x80041006</span></span> | <span data-ttu-id="eab63-121">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um das Objekt zu klonen.</span><span class="sxs-lookup"><span data-stu-id="eab63-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="eab63-122">0</span><span class="sxs-lookup"><span data-stu-id="eab63-122">0</span></span> | <span data-ttu-id="eab63-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="eab63-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="eab63-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eab63-124">Remarks</span></span>

<span data-ttu-id="eab63-125">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="eab63-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="eab63-126">Das geklonte Objekt ist ein COM-Objekt mit einer Verweisanzahl von 1.</span><span class="sxs-lookup"><span data-stu-id="eab63-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="eab63-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eab63-127">Requirements</span></span>  
 <span data-ttu-id="eab63-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eab63-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eab63-129">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eab63-129">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="eab63-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="eab63-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eab63-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eab63-131">See also</span></span>

- [<span data-ttu-id="eab63-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="eab63-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
