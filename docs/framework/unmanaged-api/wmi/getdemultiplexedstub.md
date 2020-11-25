---
title: Getdemultiplexedstub-Funktion (Referenz zur nicht verwalteten API)
description: Die getdemultiplexedstub-Funktion erstellt eine Objekt Weiterleitungs Senke, um einem Client den Empfang von asynchronen Aufrufen von der Windows-Verwaltung zu unterstützen.
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
ms.openlocfilehash: f8f9b56268168bb16c476a9366facd17e8ac44e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730629"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="0efb4-103">GetDemultiplexedStub-Funktion</span><span class="sxs-lookup"><span data-stu-id="0efb4-103">GetDemultiplexedStub function</span></span>

<span data-ttu-id="0efb4-104">Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0efb4-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0efb4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0efb4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="0efb4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0efb4-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="0efb4-107">in Ein Zeiger auf die Prozess interne Implementierung von [iwbemubjectsink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)des Clients.</span><span class="sxs-lookup"><span data-stu-id="0efb4-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="0efb4-108">in Ein Flag, das angibt, ob das Ereignis local () ist, `true` andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="0efb4-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="0efb4-109">vorgenommen Eine-Objekt Weiterleitungs Senke, die einem Client den Empfang von asynchronen Aufrufen von der Windows-Verwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0efb4-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="0efb4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0efb4-110">Return value</span></span>

<span data-ttu-id="0efb4-111">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="0efb4-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="0efb4-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="0efb4-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="0efb4-113">Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.</span><span class="sxs-lookup"><span data-stu-id="0efb4-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0efb4-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0efb4-114">Requirements</span></span>  

 <span data-ttu-id="0efb4-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0efb4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0efb4-116">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0efb4-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0efb4-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0efb4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efb4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0efb4-118">See also</span></span>

- [<span data-ttu-id="0efb4-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0efb4-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
