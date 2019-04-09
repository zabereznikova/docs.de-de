---
title: ICorDebugModule::GetBaseAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 763f2872099fac87138b7e1ab058c60475892b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107418"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="e77d2-102">ICorDebugModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="e77d2-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="e77d2-103">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="e77d2-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e77d2-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e77d2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e77d2-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="e77d2-106">[out] Ein `CORDB_ADDRESS` , der die Basisadresse des Moduls angibt.</span><span class="sxs-lookup"><span data-stu-id="e77d2-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e77d2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e77d2-107">Remarks</span></span>  
 <span data-ttu-id="e77d2-108">Das Modul ist ein systemeigenes Image erstellen (d.h., wenn das Modul vom des native Image Generator, NGen.exe erstellt wurde), der Basisadresse ist 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="e77d2-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77d2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e77d2-109">Requirements</span></span>  
 <span data-ttu-id="e77d2-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e77d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e77d2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e77d2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e77d2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e77d2-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e77d2-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e77d2-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e77d2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e77d2-114">See also</span></span>
