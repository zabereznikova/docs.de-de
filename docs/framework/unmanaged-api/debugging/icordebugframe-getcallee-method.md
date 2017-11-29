---
title: ICorDebugFrame::GetCallee-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54a26ad7d4818aae81b765ab4e6c0e5be821680e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="e7346-102">ICorDebugFrame::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="e7346-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="e7346-103">Ruft einen Zeiger auf das ICorDebugFrame-Objekt in der aktuellen Kette, die dieses Rahmens aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e7346-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7346-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7346-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7346-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7346-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="e7346-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugFrame` Objekt, das den aufgerufenen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7346-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="e7346-107">Dieser Wert ist null, wenn der aufrufende Frame der innerste Rahmen in der aktuellen Kette ist.</span><span class="sxs-lookup"><span data-stu-id="e7346-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7346-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7346-108">Requirements</span></span>  
 <span data-ttu-id="e7346-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7346-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7346-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7346-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7346-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7346-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7346-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7346-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
