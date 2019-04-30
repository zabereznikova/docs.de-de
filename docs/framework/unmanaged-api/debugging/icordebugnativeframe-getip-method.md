---
title: ICorDebugNativeFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987968"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="cbfee-102">ICorDebugNativeFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="cbfee-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="cbfee-103">Ruft der systemeigene Code offset-Speicherort, der der Anweisungszeiger derzeit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cbfee-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbfee-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbfee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbfee-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="cbfee-106">[out] Ein Zeiger auf die Offsetposition im nativen Code.</span><span class="sxs-lookup"><span data-stu-id="cbfee-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbfee-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbfee-107">Remarks</span></span>  
 <span data-ttu-id="cbfee-108">Wenn der Stapelrahmen, der durch diesen "ICorDebugNativeFrame" dargestellt wird, aktiv ist, ist der Offset der Adresse, der die nächste Anweisung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cbfee-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="cbfee-109">Wenn dieses Stapelrahmens nicht aktiv ist, ist der Offset der Adresse der nächsten Anweisung wird ausgeführt, wenn der Stapelrahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="cbfee-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfee-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbfee-110">Requirements</span></span>  
 <span data-ttu-id="cbfee-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbfee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbfee-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbfee-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbfee-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbfee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbfee-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbfee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfee-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbfee-115">See also</span></span>
