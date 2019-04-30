---
title: ICorDebugFunction::GetCurrentVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988727"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="6dc1c-102">ICorDebugFunction::GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="6dc1c-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="6dc1c-103">Ruft die Versionsnummer der letzten Änderung der Funktion, die von diesem ICorDebugFunction-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6dc1c-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dc1c-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dc1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6dc1c-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="6dc1c-106">[out] Ein Zeiger auf einen ganzzahligen Wert, der die Versionsnummer der letzten Änderung für diese Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="6dc1c-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dc1c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6dc1c-107">Remarks</span></span>  
 <span data-ttu-id="6dc1c-108">Die Versionsnummer der letzten Änderung für diese Funktion möglicherweise größer als die Versionsnummer der Funktion selbst.</span><span class="sxs-lookup"><span data-stu-id="6dc1c-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="6dc1c-109">Verwenden Sie entweder die [ICorDebugFunction2:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) Methode oder der [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) Methode, um die Versionsnummer der Funktion abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6dc1c-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc1c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6dc1c-110">Requirements</span></span>  
 <span data-ttu-id="6dc1c-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dc1c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc1c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dc1c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dc1c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dc1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dc1c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dc1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
