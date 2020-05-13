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
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210318"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="aba29-102">ICorDebugILFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="aba29-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="aba29-103">Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="aba29-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aba29-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aba29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aba29-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="aba29-106">in Die gewünschte Einstellung für den Anweisungs Zeiger.</span><span class="sxs-lookup"><span data-stu-id="aba29-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aba29-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aba29-107">Remarks</span></span>  
 <span data-ttu-id="aba29-108">Verwenden Sie die- `CanSetIP` Methode, bevor Sie die [ICorDebugILFrame:: abtip](icordebugilframe-setip-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aba29-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="aba29-109">Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie trotzdem aufrufen `ICorDebugILFrame::SetIP` , aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="aba29-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba29-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aba29-110">Requirements</span></span>  
 <span data-ttu-id="aba29-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba29-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba29-112">**Header:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="aba29-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="aba29-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aba29-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aba29-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aba29-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
