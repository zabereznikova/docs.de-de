---
title: ICorDebugThread::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: 8928e22b70af0360660c30289ee999a3e4c5e99e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133473"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="f3f05-102">ICorDebugThread::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f3f05-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="f3f05-103">Ruft einen Schnittstellen Zeiger auf den Prozess ab, von dem dieser ICorDebugThread ein Part bildet.</span><span class="sxs-lookup"><span data-stu-id="f3f05-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3f05-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3f05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3f05-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="f3f05-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellen Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f3f05-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3f05-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3f05-107">Requirements</span></span>  
 <span data-ttu-id="f3f05-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f05-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3f05-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3f05-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3f05-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3f05-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
