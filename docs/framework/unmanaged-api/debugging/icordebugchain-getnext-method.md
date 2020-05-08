---
title: ICorDebugChain::GetNext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
ms.openlocfilehash: 47a90ed63ae217cb150f392ad9196f8d0d5764e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894643"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="530ca-102">ICorDebugChain::GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="530ca-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="530ca-103">Ruft die nächste Rahmen Kette für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="530ca-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="530ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="530ca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="530ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="530ca-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="530ca-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die nächste Kette von Frames für den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="530ca-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="530ca-107">Wenn diese Kette die letzte Kette ist, `ppChain` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="530ca-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="530ca-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="530ca-108">Requirements</span></span>  
 <span data-ttu-id="530ca-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="530ca-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530ca-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="530ca-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="530ca-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="530ca-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="530ca-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="530ca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
