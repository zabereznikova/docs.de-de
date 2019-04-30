---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7c72d0766580f9aa3aa678aacd872b804172a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940217"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="be2e4-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="be2e4-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="be2e4-103">Finden Sie unter [DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="be2e4-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be2e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be2e4-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be2e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be2e4-105">Parameters</span></span>  
  
|<span data-ttu-id="be2e4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="be2e4-106">Parameter</span></span>|<span data-ttu-id="be2e4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be2e4-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="be2e4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="be2e4-108">Return Value</span></span>  
 <span data-ttu-id="be2e4-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="be2e4-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be2e4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be2e4-110">Requirements</span></span>  
 <span data-ttu-id="be2e4-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="be2e4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2e4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be2e4-112">See also</span></span>

- [<span data-ttu-id="be2e4-113">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be2e4-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
