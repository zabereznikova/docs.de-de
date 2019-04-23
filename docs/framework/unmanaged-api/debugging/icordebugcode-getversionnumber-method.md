---
title: ICorDebugCode::GetVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003b29501e8f22ed9010a9f16a4f7ee67bce03a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098948"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="9f0e4-102">ICorDebugCode::GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="9f0e4-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="9f0e4-103">Ruft ab, die mit eins beginnende Zahl, die die Version des Codes, die identifiziert "ICorDebugCode" darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f0e4-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f0e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f0e4-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="9f0e4-106">[out] Ein Zeiger auf die Versionsnummer des Codes.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f0e4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f0e4-107">Remarks</span></span>  
 <span data-ttu-id="9f0e4-108">Die Versionsnummer wird jedes Mal inkrementiert, die ein Vorgang für bearbeiten und Fortfahren (EnC) für den Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f0e4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f0e4-109">Requirements</span></span>  
 <span data-ttu-id="9f0e4-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0e4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0e4-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f0e4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f0e4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f0e4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f0e4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0e4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0e4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f0e4-114">See also</span></span>
