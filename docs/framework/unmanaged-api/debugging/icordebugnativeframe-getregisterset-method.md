---
title: ICorDebugNativeFrame::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a4f7ecc227679e6b0afa29b20de1aefeae3b76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077921"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="cb257-102">ICorDebugNativeFrame::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="cb257-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="cb257-103">Ruft das Register, legen Sie für diesen Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="cb257-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb257-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb257-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb257-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb257-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="cb257-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Objekt, das Register darstellt, die für dieses Stapelrahmens festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb257-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb257-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb257-107">Requirements</span></span>  
 <span data-ttu-id="cb257-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb257-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb257-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb257-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb257-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb257-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cb257-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cb257-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb257-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb257-112">See also</span></span>
