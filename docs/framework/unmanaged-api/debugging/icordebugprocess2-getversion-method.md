---
title: ICorDebugProcess2::GetVersion-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1f850e85099a466c497a8fcc822bce9510f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416379"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="d1f48-102">ICorDebugProcess2::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f48-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="d1f48-103">Ruft die Versionsnummer der common Language Runtime (CLR), die in diesem Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d1f48-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1f48-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1f48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1f48-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="d1f48-106">[out] Ein Zeiger auf eine COR_VERSION-Struktur, die die Versionsnummer der Runtime gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1f48-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1f48-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1f48-107">Remarks</span></span>  
 <span data-ttu-id="d1f48-108">Die `GetVersion` Methode wird ein Fehlercode zurückgegeben, wenn keine Common Language Runtime im Prozess geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="d1f48-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f48-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1f48-109">Requirements</span></span>  
 <span data-ttu-id="d1f48-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f48-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1f48-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1f48-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1f48-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1f48-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
