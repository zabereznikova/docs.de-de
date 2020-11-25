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
ms.openlocfilehash: 9049cd42e9c10cdcff62b005094b56c9df9ce975
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719995"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="7d3d0-102">INotifySink2::OnSyncCallExit-Methode</span><span class="sxs-lookup"><span data-stu-id="7d3d0-102">INotifySink2::OnSyncCallExit Method</span></span>

<span data-ttu-id="7d3d0-103">Wird aufgerufen, wenn ein Aufruf beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d3d0-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d3d0-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d3d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d3d0-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="7d3d0-106">in ID des aufzurufenden Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7d3d0-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="7d3d0-107">Siehe [CALL_ID Struktur](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7d3d0-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="7d3d0-108">vorgenommen Der Rückruf Puffer.</span><span class="sxs-lookup"><span data-stu-id="7d3d0-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="7d3d0-109">vorgenommen Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7d3d0-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d3d0-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d3d0-110">Return Value</span></span>  

 <span data-ttu-id="7d3d0-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7d3d0-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d3d0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7d3d0-112">Requirements</span></span>  

 <span data-ttu-id="7d3d0-113">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="7d3d0-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3d0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d3d0-114">See also</span></span>

- [<span data-ttu-id="7d3d0-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d3d0-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="7d3d0-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d3d0-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="7d3d0-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d3d0-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
