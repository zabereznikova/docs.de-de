---
title: Clone-Funktion (Referenz zur nicht verwalteten API)
description: "Die Klon-Funktion gibt ein neues Objekt, das eine vollständige Klon der aktuellen Instanz ist."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Clone
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Clone
helpviewer_keywords: Clone function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6a089f66ddd6f8f9a2d5677dd8dd6917fcb719
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="clone-function"></a><span data-ttu-id="2e0ac-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="2e0ac-103">Clone function</span></span>
<span data-ttu-id="2e0ac-104">Gibt ein neues Objekt, das eine vollständige Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2e0ac-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e0ac-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="2e0ac-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e0ac-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2e0ac-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2e0ac-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="2e0ac-109">[out] Ein neues Objekt, das eine vollständige ist der einzige `ptr`.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="2e0ac-110">Dieses Argument nicht mit `null` Empfang die Kopie des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="2e0ac-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e0ac-111">Return value</span></span>

<span data-ttu-id="2e0ac-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="2e0ac-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2e0ac-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="2e0ac-113">Constant</span></span>  |<span data-ttu-id="2e0ac-114">Wert</span><span class="sxs-lookup"><span data-stu-id="2e0ac-114">Value</span></span>  |<span data-ttu-id="2e0ac-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e0ac-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2e0ac-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="2e0ac-116">0x80041001</span></span> | <span data-ttu-id="2e0ac-117">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2e0ac-118">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="2e0ac-118">0x80041008</span></span> | <span data-ttu-id="2e0ac-119">`null`als Parameter angegeben wurde, und es ist nicht zulässig, bei dieser Verwendung.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2e0ac-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2e0ac-120">0x80041006</span></span> | <span data-ttu-id="2e0ac-121">Es ist nicht genügend Arbeitsspeicher verfügbar, wenn das Objekt geklont.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2e0ac-122">0</span><span class="sxs-lookup"><span data-stu-id="2e0ac-122">0</span></span> | <span data-ttu-id="2e0ac-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2e0ac-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e0ac-124">Remarks</span></span>

<span data-ttu-id="2e0ac-125">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2e0ac-126">Das geklonte Objekt ist ein COM-Objekt, das eine Verweisanzahl von 1 hat.</span><span class="sxs-lookup"><span data-stu-id="2e0ac-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e0ac-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e0ac-127">Requirements</span></span>  
 <span data-ttu-id="2e0ac-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ac-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0ac-129">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2e0ac-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2e0ac-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0ac-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0ac-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e0ac-131">See also</span></span>  
[<span data-ttu-id="2e0ac-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2e0ac-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
