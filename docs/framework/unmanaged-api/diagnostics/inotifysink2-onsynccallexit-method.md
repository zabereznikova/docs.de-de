---
title: INotifySink2::OnSyncCallExit-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fe2ebecdacd3b848d5de7eecca4753a89a58f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432478"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="85c89-102">INotifySink2::OnSyncCallExit-Methode</span><span class="sxs-lookup"><span data-stu-id="85c89-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="85c89-103">Wird aufgerufen, wenn ein Aufruf beendet wird.</span><span class="sxs-lookup"><span data-stu-id="85c89-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85c89-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85c89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85c89-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="85c89-106">[in] Die ID des Aufrufs wird beendet.</span><span class="sxs-lookup"><span data-stu-id="85c89-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="85c89-107">Finden Sie unter [CALL_ID-Struktur](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="85c89-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="85c89-108">[out] Rufen Sie die Puffer.</span><span class="sxs-lookup"><span data-stu-id="85c89-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="85c89-109">[out] Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="85c89-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85c89-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85c89-110">Return Value</span></span>  
 <span data-ttu-id="85c89-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="85c89-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c89-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85c89-112">Requirements</span></span>  
 <span data-ttu-id="85c89-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="85c89-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c89-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85c89-114">See Also</span></span>  
 [<span data-ttu-id="85c89-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85c89-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="85c89-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85c89-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="85c89-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85c89-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
