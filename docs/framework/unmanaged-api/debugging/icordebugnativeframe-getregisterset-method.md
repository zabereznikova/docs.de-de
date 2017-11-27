---
title: ICorDebugNativeFrame::GetRegisterSet-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7689632d41971d85417501e9a7f90712a07b34bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="a3a21-102">ICorDebugNativeFrame::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="a3a21-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="a3a21-103">Ruft den Registersatz für diesen Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="a3a21-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3a21-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3a21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3a21-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="a3a21-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Objekt, das Register darstellt, die für dieses Stapelrahmens festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a3a21-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a21-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3a21-107">Requirements</span></span>  
 <span data-ttu-id="a3a21-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3a21-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a21-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3a21-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3a21-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3a21-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3a21-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a21-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a21-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3a21-112">See Also</span></span>  
 
