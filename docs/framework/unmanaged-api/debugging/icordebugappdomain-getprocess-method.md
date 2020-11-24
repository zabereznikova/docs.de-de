---
title: ICorDebugAppDomain::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
ms.openlocfilehash: 6521341499df52c1851401f3f2f5c48a3b68ccd3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675957"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="a26ed-102">ICorDebugAppDomain::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="a26ed-102">ICorDebugAppDomain::GetProcess Method</span></span>

<span data-ttu-id="a26ed-103">Ruft den Prozess ab, der die Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="a26ed-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a26ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a26ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a26ed-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="a26ed-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="a26ed-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a26ed-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a26ed-107">Requirements</span></span>  

 <span data-ttu-id="a26ed-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a26ed-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a26ed-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a26ed-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a26ed-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a26ed-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a26ed-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a26ed-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
