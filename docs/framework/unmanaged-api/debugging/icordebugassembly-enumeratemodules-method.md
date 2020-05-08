---
title: ICorDebugAssembly::EnumerateModules-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
ms.openlocfilehash: 12dc5466d5be73b327f171c389c41c55901f2915
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894954"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="d52f0-102">ICorDebugAssembly::EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="d52f0-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="d52f0-103">Ruft einen Enumerator für die Module ab, die `ICorDebugAssembly`in der enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d52f0-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d52f0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d52f0-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="d52f0-106">vorgenommen Ein Zeiger auf die Adresse der icorentbugmoduleenumeration-Schnittstelle, die der Enumerator ist.</span><span class="sxs-lookup"><span data-stu-id="d52f0-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52f0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d52f0-107">Requirements</span></span>  
 <span data-ttu-id="d52f0-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52f0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52f0-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d52f0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d52f0-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d52f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d52f0-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
