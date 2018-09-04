---
title: GetDemultiplexedStub-Funktion (Referenz zur nicht verwalteten API)
description: Die GetDemultiplexedStub-Funktion erstellt, eine Objektsenke für die Weiterleitung, bei der ein Client asynchrone Aufrufe aus der Windows-Verwaltung empfangen wird.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659198"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="6f9cf-103">GetDemultiplexedStub-Funktion</span><span class="sxs-lookup"><span data-stu-id="6f9cf-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="6f9cf-104">Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6f9cf-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6f9cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f9cf-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="6f9cf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f9cf-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="6f9cf-107">[in] Ein Zeiger auf dem Client in-Process-Implementierung von [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="6f9cf-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="6f9cf-108">[in] Ein Flag, das angibt, ob das Ereignis lokal ist (`true`) ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6f9cf-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="6f9cf-109">[out] Eine Weiterleitung Objektsenke bei einem Client beim Empfang von asynchroner Aufrufen von der Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="6f9cf-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="6f9cf-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f9cf-110">Return value</span></span>

<span data-ttu-id="6f9cf-111">Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="6f9cf-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="6f9cf-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein NULL-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6f9cf-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="6f9cf-113">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="6f9cf-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="6f9cf-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f9cf-114">Requirements</span></span>  
 <span data-ttu-id="6f9cf-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f9cf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f9cf-116">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6f9cf-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6f9cf-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6f9cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9cf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f9cf-118">See also</span></span>  
[<span data-ttu-id="6f9cf-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="6f9cf-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
