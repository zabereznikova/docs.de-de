---
title: ICorDebugRegisterSet::SetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: eba86c09197aad6bac284c52fe164432e197c6f7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378250"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="21158-102">ICorDebugRegisterSet::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="21158-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="21158-103">`SetRegisters`ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="21158-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="21158-104">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="21158-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21158-105">Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="21158-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21158-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="21158-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="21158-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21158-107">Requirements</span></span>  
 <span data-ttu-id="21158-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21158-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21158-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21158-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21158-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21158-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21158-111">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="21158-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21158-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21158-112">See also</span></span>

- [<span data-ttu-id="21158-113">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21158-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="21158-114">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21158-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
