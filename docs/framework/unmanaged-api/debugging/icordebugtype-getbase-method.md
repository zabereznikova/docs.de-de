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
ms.openlocfilehash: 967f8f25e240f484ae86852c740be12cd3a6409e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681820"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="478a2-102">ICorDebugType::GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="478a2-102">ICorDebugType::GetBase Method</span></span>

<span data-ttu-id="478a2-103">Ruft einen Schnittstellen Zeiger auf einen ICorDebugType ab, der den Basistyp des Typs darstellt, der von diesem dargestellt wird `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="478a2-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="478a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="478a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="478a2-105">Parameters</span></span>  

 `pBase`  
 <span data-ttu-id="478a2-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den Basistyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="478a2-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="478a2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="478a2-107">Remarks</span></span>  

 <span data-ttu-id="478a2-108">Das Suchen des Basistyps für einen Typ ist nützlich, um allgemeine Debuggerfunktionen zu implementieren, wie z. b. das Drucken aller Felder eines Objekts oder der übergeordneten Klassen.</span><span class="sxs-lookup"><span data-stu-id="478a2-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="478a2-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="478a2-109">Requirements</span></span>  

 <span data-ttu-id="478a2-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="478a2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="478a2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="478a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="478a2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="478a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="478a2-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="478a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
