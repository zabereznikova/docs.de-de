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
ms.openlocfilehash: 9cc028b3300b43f8a0fb3e29f8b5ac6e1817b8c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127473"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="37403-103">Getdemultiplexedstub-Funktion</span><span class="sxs-lookup"><span data-stu-id="37403-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="37403-104">Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="37403-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="37403-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="37403-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="37403-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="37403-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="37403-107">in Ein Zeiger auf die Prozess interne Implementierung von [iwbemubjectsink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)des Clients.</span><span class="sxs-lookup"><span data-stu-id="37403-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="37403-108">in Ein Flag, das angibt, ob das Ereignis lokal (`true`) ist; Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="37403-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="37403-109">vorgenommen Eine-Objekt Weiterleitungs Senke, die einem Client den Empfang von asynchronen Aufrufen von der Windows-Verwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37403-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="37403-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37403-110">Return value</span></span>

<span data-ttu-id="37403-111">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="37403-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="37403-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="37403-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="37403-113">Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.</span><span class="sxs-lookup"><span data-stu-id="37403-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="37403-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37403-114">Requirements</span></span>  
 <span data-ttu-id="37403-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37403-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37403-116">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="37403-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="37403-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37403-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37403-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37403-118">See also</span></span>

- [<span data-ttu-id="37403-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="37403-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
