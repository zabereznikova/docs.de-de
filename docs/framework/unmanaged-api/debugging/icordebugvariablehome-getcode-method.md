---
title: ICorDebugVariableHome::GetCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4cadae7a43d0cd965e51535eae2c95e59900d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130012"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="8d520-102">ICorDebugVariableHome::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="8d520-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="8d520-103">Ruft die Instanz von "ICorDebugCode", der diesen [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="8d520-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d520-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d520-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d520-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d520-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="8d520-106">[out] Ein Zeiger auf die Adresse der Instanz "ICorDebugCode", der diesen [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="8d520-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d520-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d520-107">Requirements</span></span>  
 <span data-ttu-id="8d520-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d520-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d520-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d520-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d520-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d520-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8d520-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8d520-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d520-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d520-112">See also</span></span>

- [<span data-ttu-id="8d520-113">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d520-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
