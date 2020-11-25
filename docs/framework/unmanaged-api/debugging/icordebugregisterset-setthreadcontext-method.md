---
title: ICorDebugRegisterSet::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 66e8cf3f73e92f58765b1fa98b3eef11b976094c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712273"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="68545-102">ICorDebugRegisterSet::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="68545-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>

<span data-ttu-id="68545-103">`SetThreadContext` ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="68545-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="68545-104">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="68545-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68545-105">Verwenden Sie den übergeordneten Vorgang [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) , um den Kontext eines Threads festzulegen.</span><span class="sxs-lookup"><span data-stu-id="68545-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68545-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="68545-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="68545-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68545-107">Requirements</span></span>  

 <span data-ttu-id="68545-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68545-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68545-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68545-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68545-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68545-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68545-111">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="68545-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68545-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68545-112">See also</span></span>

- [<span data-ttu-id="68545-113">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68545-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="68545-114">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68545-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
