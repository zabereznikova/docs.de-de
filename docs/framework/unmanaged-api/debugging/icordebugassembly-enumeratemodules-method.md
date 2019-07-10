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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1d8d76084bcf0b5951c6431c6f21f352406050b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737373"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="c1f5f-102">ICorDebugAssembly::EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="c1f5f-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="c1f5f-103">Ruft einen Enumerator ab, für die Module, die innerhalb der `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="c1f5f-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1f5f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1f5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1f5f-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="c1f5f-106">[out] Ein Zeiger auf die Adresse der ICorDebugModuleEnum-Schnittstelle, die der Enumerator ist.</span><span class="sxs-lookup"><span data-stu-id="c1f5f-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1f5f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1f5f-107">Requirements</span></span>  
 <span data-ttu-id="c1f5f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1f5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1f5f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1f5f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1f5f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1f5f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1f5f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1f5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
