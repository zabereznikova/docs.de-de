---
title: ICorDebugEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 28e0cded33b49e3aadc0564bae3a60bee76c4396
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677387"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="5a6f4-102">ICorDebugEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="5a6f4-102">ICorDebugEnum::Clone Method</span></span>

<span data-ttu-id="5a6f4-103">Erstellt eine Kopie dieses ICorDebugEnum-Objekts.</span><span class="sxs-lookup"><span data-stu-id="5a6f4-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a6f4-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a6f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a6f4-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5a6f4-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugEnum` Objekts, das eine Kopie dieses Objekts ist `ICorDebugEnum` .</span><span class="sxs-lookup"><span data-stu-id="5a6f4-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6f4-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5a6f4-107">Requirements</span></span>  

 <span data-ttu-id="5a6f4-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a6f4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6f4-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a6f4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a6f4-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a6f4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a6f4-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6f4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
