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
ms.openlocfilehash: 99c80fba594e9eaf69a3cc9a025509aa4c3c26a4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703303"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="1c28f-102">ICorDebugILFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="1c28f-102">ICorDebugILFrame::CanSetIP Method</span></span>

<span data-ttu-id="1c28f-103">Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1c28f-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c28f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c28f-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c28f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c28f-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="1c28f-106">in Die gewünschte Einstellung für den Anweisungs Zeiger.</span><span class="sxs-lookup"><span data-stu-id="1c28f-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c28f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c28f-107">Remarks</span></span>  

 <span data-ttu-id="1c28f-108">Verwenden Sie die- `CanSetIP` Methode, bevor Sie die [ICorDebugILFrame:: abtip](icordebugilframe-setip-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1c28f-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="1c28f-109">Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie trotzdem aufrufen `ICorDebugILFrame::SetIP` , aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="1c28f-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c28f-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1c28f-110">Requirements</span></span>  

 <span data-ttu-id="1c28f-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c28f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c28f-112">**Header:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="1c28f-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="1c28f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c28f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c28f-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c28f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
