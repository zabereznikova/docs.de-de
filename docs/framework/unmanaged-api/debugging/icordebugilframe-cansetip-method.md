---
title: ICorDebugILFrame::CanSetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 57d83d1f301cbfd43f8f553d9aef4beb3baf95f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131085"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="8f96c-102">ICorDebugILFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="8f96c-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="8f96c-103">Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8f96c-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f96c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f96c-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f96c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f96c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="8f96c-106">in Die gewünschte Einstellung für den Anweisungs Zeiger.</span><span class="sxs-lookup"><span data-stu-id="8f96c-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f96c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f96c-107">Remarks</span></span>  
 <span data-ttu-id="8f96c-108">Verwenden Sie die `CanSetIP`-Methode, bevor Sie die [ICorDebugILFrame:: abtip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8f96c-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="8f96c-109">Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie weiterhin `ICorDebugILFrame::SetIP`aufrufen, aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="8f96c-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f96c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f96c-110">Requirements</span></span>  
 <span data-ttu-id="8f96c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f96c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f96c-112">**Header:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="8f96c-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="8f96c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f96c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f96c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f96c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
