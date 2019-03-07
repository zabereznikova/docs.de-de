---
title: INotifySink2::OnSyncCallReturn-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae3067e6941451d4debd8d18ca58a91708a48e56
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487235"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="c4865-102">INotifySink2::OnSyncCallReturn-Methode</span><span class="sxs-lookup"><span data-stu-id="c4865-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="c4865-103">Wird aufgerufen, wenn ein Aufruf zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c4865-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4865-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4865-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4865-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4865-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="c4865-106">[in] Die ID des Aufrufs von zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c4865-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="c4865-107">Finden Sie unter [CALL_ID-Struktur](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="c4865-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="c4865-108">[in] Rufen Sie die Puffer.</span><span class="sxs-lookup"><span data-stu-id="c4865-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="c4865-109">[in] Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c4865-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4865-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4865-110">Return Value</span></span>  
 <span data-ttu-id="c4865-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c4865-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4865-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4865-112">Requirements</span></span>  
 <span data-ttu-id="c4865-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="c4865-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4865-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4865-114">See also</span></span>
- [<span data-ttu-id="c4865-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4865-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="c4865-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4865-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="c4865-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4865-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
