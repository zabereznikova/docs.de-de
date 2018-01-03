---
title: ICorDebugInternalFrame::GetFrameType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame.GetFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 476903ae8f1461a46d685bc3e549c3b6553d5c68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="781dc-102">ICorDebugInternalFrame::GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="781dc-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="781dc-103">Ruft den Typ dieses interne Rahmens ab.</span><span class="sxs-lookup"><span data-stu-id="781dc-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="781dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="781dc-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="781dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="781dc-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="781dc-106">[out] Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ des internen Frames dargestellt, die von diesem angibt `ICorDebugInternalFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="781dc-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="781dc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="781dc-107">Remarks</span></span>  
 <span data-ttu-id="781dc-108">Der interne Rahmentyp wird nie STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="781dc-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="781dc-109">Debugger sollten nicht erkannte interne Rahmentypen ordnungsgemäß ignorieren.</span><span class="sxs-lookup"><span data-stu-id="781dc-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="781dc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="781dc-110">Requirements</span></span>  
 <span data-ttu-id="781dc-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="781dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="781dc-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="781dc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="781dc-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="781dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="781dc-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="781dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
