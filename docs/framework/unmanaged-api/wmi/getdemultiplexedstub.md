---
title: GetDemultiplexedStub-Funktion (Referenz zur nicht verwalteten API)
description: Die GetDemultiplexedStub-Funktion erstellt eine Objekt Weiterleitung eine Ereignissenke, bei der ein Client asynchrone Aufrufe von Windows-Verwaltung empfangen.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a81101acbf65546ea068e6b5a0e8d9045aaadc71
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="c7e84-103">GetDemultiplexedStub-Funktion</span><span class="sxs-lookup"><span data-stu-id="c7e84-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="c7e84-104">Erstellt eine Objekt Weiterleitung eine Ereignissenke, bei der ein Client asynchrone Aufrufe von Windows-Verwaltung empfangen.</span><span class="sxs-lookup"><span data-stu-id="c7e84-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c7e84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7e84-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="c7e84-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7e84-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="c7e84-107">[in] Ein Zeiger auf den Client in-Process-Implementierung von [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="c7e84-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).</span></span>

`isLocal`  
<span data-ttu-id="c7e84-108">[in] Ein Flag, das angibt, ob das Ereignis lokal ist (`true`) ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c7e84-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="c7e84-109">[out] Ein Objekt Weiterleitung Senke eines Clients bei der asynchrone Aufrufe von Windows-Verwaltung empfangen.</span><span class="sxs-lookup"><span data-stu-id="c7e84-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="c7e84-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7e84-110">Return value</span></span>

<span data-ttu-id="c7e84-111">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="c7e84-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="c7e84-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c7e84-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="c7e84-113">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="c7e84-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="c7e84-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7e84-114">Requirements</span></span>  
 <span data-ttu-id="c7e84-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7e84-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7e84-116">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c7e84-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c7e84-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e84-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e84-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e84-118">See also</span></span>  
[<span data-ttu-id="c7e84-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="c7e84-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
