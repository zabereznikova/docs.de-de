---
title: ICorDebugType::GetBase-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d04bc67013a2227f295ac3a41be027b9f9b04e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946307"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="f0f57-102">ICorDebugType::GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="f0f57-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="f0f57-103">Ruft einen Schnittstellenzeiger einen ICorDebugType, der den Basistyp darstellt, sofern vorhanden, der dem Typ zugeordnet, die von diesem `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f0f57-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0f57-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0f57-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="f0f57-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugType` -Objekt, das den Basistyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0f57-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f57-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0f57-107">Remarks</span></span>  
 <span data-ttu-id="f0f57-108">Suche nach der Basistyp für einen Typ ist hilfreich, die allgemeine Funktionalität für den Debugger, z. B. das ausgeben, die alle Felder eines Objekts oder die übergeordneten Klassen implementieren.</span><span class="sxs-lookup"><span data-stu-id="f0f57-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f57-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0f57-109">Requirements</span></span>  
 <span data-ttu-id="f0f57-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0f57-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f57-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0f57-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0f57-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0f57-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0f57-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
