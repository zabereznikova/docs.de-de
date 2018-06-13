---
title: Clone-Funktion (Referenz zur nicht verwalteten API)
description: Die Klon-Funktion gibt ein neues Objekt, das eine vollständige Klon der aktuellen Instanz ist.
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
ms.openlocfilehash: c5841c89cf394502f68381dfed42593c9debdcb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457315"
---
# <a name="clone-function"></a><span data-ttu-id="f0026-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="f0026-103">Clone function</span></span>
<span data-ttu-id="f0026-104">Gibt ein neues Objekt, das eine vollständige Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="f0026-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f0026-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0026-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="f0026-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0026-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f0026-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0026-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f0026-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="f0026-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="f0026-109">[out] Ein neues Objekt, das eine vollständige ist der einzige `ptr`.</span><span class="sxs-lookup"><span data-stu-id="f0026-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="f0026-110">Dieses Argument nicht mit `null` Empfang die Kopie des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="f0026-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0026-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0026-111">Return value</span></span>

<span data-ttu-id="f0026-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="f0026-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f0026-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="f0026-113">Constant</span></span>  |<span data-ttu-id="f0026-114">Wert</span><span class="sxs-lookup"><span data-stu-id="f0026-114">Value</span></span>  |<span data-ttu-id="f0026-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0026-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f0026-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="f0026-116">0x80041001</span></span> | <span data-ttu-id="f0026-117">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0026-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f0026-118">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="f0026-118">0x80041008</span></span> | <span data-ttu-id="f0026-119">`null` als Parameter angegeben wurde, und es ist nicht zulässig, bei dieser Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f0026-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f0026-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f0026-120">0x80041006</span></span> | <span data-ttu-id="f0026-121">Es ist nicht genügend Arbeitsspeicher verfügbar, wenn das Objekt geklont.</span><span class="sxs-lookup"><span data-stu-id="f0026-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f0026-122">0</span><span class="sxs-lookup"><span data-stu-id="f0026-122">0</span></span> | <span data-ttu-id="f0026-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f0026-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f0026-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0026-124">Remarks</span></span>

<span data-ttu-id="f0026-125">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="f0026-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="f0026-126">Das geklonte Objekt ist ein COM-Objekt, das eine Verweisanzahl von 1 hat.</span><span class="sxs-lookup"><span data-stu-id="f0026-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0026-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0026-127">Requirements</span></span>  
 <span data-ttu-id="f0026-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0026-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0026-129">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f0026-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f0026-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f0026-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0026-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0026-131">See also</span></span>  
[<span data-ttu-id="f0026-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f0026-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
