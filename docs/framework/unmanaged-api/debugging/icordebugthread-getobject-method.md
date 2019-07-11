---
title: ICorDebugThread::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3695f150797e6a59a2fb1d58c99f233a35d687ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771845"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="e4aba-102">ICorDebugThread::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e4aba-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="e4aba-103">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="e4aba-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4aba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4aba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4aba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4aba-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e4aba-106">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugValue-Schnittstelle, die den CLR-Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4aba-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4aba-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4aba-107">Requirements</span></span>  
 <span data-ttu-id="e4aba-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4aba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4aba-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4aba-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4aba-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4aba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4aba-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4aba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4aba-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4aba-112">See also</span></span>

- <xref:System.Threading.Thread>
