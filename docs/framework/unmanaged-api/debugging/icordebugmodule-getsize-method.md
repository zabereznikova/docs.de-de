---
title: ICorDebugModule::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212515"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="e2802-102">ICorDebugModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e2802-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="e2802-103">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="e2802-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2802-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2802-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2802-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2802-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="e2802-106">vorgenommen Die Größe des Moduls in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e2802-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="e2802-107">Wenn das Modul aus dem Native Image Generator (Ngen. exe) erstellt wurde, ist die Größe des Moduls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e2802-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2802-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e2802-108">Requirements</span></span>  
 <span data-ttu-id="e2802-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2802-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2802-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2802-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2802-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2802-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2802-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2802-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
