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
ms.openlocfilehash: 3011a8c7e5cf278768587633967b2e9491cf87ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137340"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="67d1c-102">ICorDebugNativeFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="67d1c-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="67d1c-103">Ruft den Speicherort des systemeigenen Codes ab, auf den der Anweisungs Zeiger aktuell festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="67d1c-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67d1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67d1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67d1c-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="67d1c-106">vorgenommen Ein Zeiger auf die Offset Position im systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="67d1c-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67d1c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67d1c-107">Remarks</span></span>  
 <span data-ttu-id="67d1c-108">Wenn der Stapel Rahmen, der durch diesen "ICorDebugNativeFrame" dargestellt wird, aktiv ist, entspricht der Offset der Adresse der nächsten Anweisung, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="67d1c-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="67d1c-109">Wenn dieser Stapel Rahmen nicht aktiv ist, ist der Offset die Adresse der nächsten Anweisung, die ausgeführt werden soll, wenn der Stapel Rahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="67d1c-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d1c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67d1c-110">Requirements</span></span>  
 <span data-ttu-id="67d1c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67d1c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d1c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67d1c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67d1c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67d1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67d1c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d1c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67d1c-115">See also</span></span>
