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
ms.openlocfilehash: 4c0cae29cceb3f23c7d09cf096937c99641d5a87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773603"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="2229f-102">ICorDebugVariableHome::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="2229f-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="2229f-103">Ruft die Instanz von "ICorDebugCode", der diesen [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="2229f-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2229f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2229f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2229f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2229f-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="2229f-106">[out] Ein Zeiger auf die Adresse der Instanz "ICorDebugCode", der diesen [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="2229f-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2229f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2229f-107">Requirements</span></span>  
 <span data-ttu-id="2229f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2229f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2229f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2229f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2229f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2229f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2229f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2229f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2229f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2229f-112">See also</span></span>

- [<span data-ttu-id="2229f-113">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2229f-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
