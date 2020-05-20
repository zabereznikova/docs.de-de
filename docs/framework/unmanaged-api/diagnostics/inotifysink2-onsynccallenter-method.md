---
title: INotifySink2::OnSyncCallEnter-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442032"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="f4833-102">INotifySink2::OnSyncCallEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="f4833-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="f4833-103">Wird aufgerufen, wenn ein-Aufruf eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f4833-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4833-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4833-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4833-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4833-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="f4833-106">in ID des aufzurufenden Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f4833-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="f4833-107">Siehe [CALL_ID Struktur](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f4833-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="f4833-108">in Der Rückruf Puffer.</span><span class="sxs-lookup"><span data-stu-id="f4833-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="f4833-109">in Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f4833-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4833-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f4833-110">Return Value</span></span>  
 <span data-ttu-id="f4833-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f4833-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4833-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4833-112">Requirements</span></span>  
 <span data-ttu-id="f4833-113">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="f4833-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4833-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4833-114">See also</span></span>

- [<span data-ttu-id="f4833-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4833-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="f4833-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4833-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="f4833-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4833-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
