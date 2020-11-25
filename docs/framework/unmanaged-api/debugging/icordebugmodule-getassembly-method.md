---
title: ICorDebugModule::GetAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: e0ae11ee24a5e25fb439d5c502c4cda5bcb6a80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710258"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="af68b-102">ICorDebugModule::GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="af68b-102">ICorDebugModule::GetAssembly Method</span></span>

<span data-ttu-id="af68b-103">Ruft die enthaltende Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="af68b-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af68b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af68b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af68b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af68b-105">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="af68b-106">vorgenommen Ein Zeiger auf ein ICorDebug-Objekt, das die Assembly darstellt, die dieses Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="af68b-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af68b-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="af68b-107">Requirements</span></span>  

 <span data-ttu-id="af68b-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af68b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af68b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af68b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af68b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af68b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af68b-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af68b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
