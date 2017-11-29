---
title: INotifySink2::OnSyncCallEnter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallEnter
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 99ffca48e33baed3a1e5700090194c1ef8c6f357
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="890d9-102">INotifySink2::OnSyncCallEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="890d9-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="890d9-103">Wird aufgerufen, wenn einen Aufruf eingeben.</span><span class="sxs-lookup"><span data-stu-id="890d9-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="890d9-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="890d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="890d9-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="890d9-106">[in] Die ID des Aufrufs eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="890d9-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="890d9-107">Finden Sie unter [CALL_ID-Struktur](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="890d9-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="890d9-108">[in] Rufen Sie die Puffer.</span><span class="sxs-lookup"><span data-stu-id="890d9-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="890d9-109">[in] Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="890d9-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="890d9-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="890d9-110">Return Value</span></span>  
 <span data-ttu-id="890d9-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="890d9-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="890d9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="890d9-112">Requirements</span></span>  
 <span data-ttu-id="890d9-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="890d9-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890d9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="890d9-114">See Also</span></span>  
 [<span data-ttu-id="890d9-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="890d9-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="890d9-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="890d9-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="890d9-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="890d9-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
