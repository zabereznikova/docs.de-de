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
ms.openlocfilehash: ee8fa8feebba7258fc84ee7ba00ce2ab1977faa4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420403"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="4b7e9-102">ICorDebugVariableHome::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="4b7e9-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="4b7e9-103">Ruft die "ICorDebugCode"-Instanz, die dieses enthält [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b7e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b7e9-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b7e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b7e9-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="4b7e9-106">[out] Ein Zeiger auf die Adresse der Instanz "ICorDebugCode", das dies enthält [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b7e9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b7e9-107">Requirements</span></span>  
 <span data-ttu-id="4b7e9-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b7e9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b7e9-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b7e9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b7e9-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b7e9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b7e9-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b7e9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7e9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b7e9-112">See Also</span></span>  
 [<span data-ttu-id="4b7e9-113">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b7e9-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 
