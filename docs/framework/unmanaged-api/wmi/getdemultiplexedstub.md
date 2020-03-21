---
title: GetDemultiplexedStub-Funktion (Nicht verwaltete API-Referenz)
description: Die GetDemultiplexedStub-Funktion erstellt eine Objektweiterleitungssensenke, um einen Client beim Empfangen asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174965"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="97bc8-103">GetDemultiplexedStub-Funktion</span><span class="sxs-lookup"><span data-stu-id="97bc8-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="97bc8-104">Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="97bc8-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="97bc8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97bc8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="97bc8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="97bc8-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="97bc8-107">[in] Ein Zeiger auf die prozessübergreifende Implementierung von [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="97bc8-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="97bc8-108">[in] Ein Flag, das angibt,`true`ob das Ereignis lokal ist ( ); andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="97bc8-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="97bc8-109">[out] Eine Objektweiterleitungssenke, um einen Client beim Empfangen asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="97bc8-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="97bc8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97bc8-110">Return value</span></span>

<span data-ttu-id="97bc8-111">Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).</span><span class="sxs-lookup"><span data-stu-id="97bc8-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="97bc8-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null.</span><span class="sxs-lookup"><span data-stu-id="97bc8-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="97bc8-113">Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.</span><span class="sxs-lookup"><span data-stu-id="97bc8-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="97bc8-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="97bc8-114">Requirements</span></span>  
 <span data-ttu-id="97bc8-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97bc8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97bc8-116">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="97bc8-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="97bc8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="97bc8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bc8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97bc8-118">See also</span></span>

- [<span data-ttu-id="97bc8-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="97bc8-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
