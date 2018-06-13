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
ms.openlocfilehash: b96c6ab8fb9065e1a08ad45a7f4482ef0b32788b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418883"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="74b81-102">ICorDebugType::GetBase-Methode</span><span class="sxs-lookup"><span data-stu-id="74b81-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="74b81-103">Ruft einen Schnittstellenzeiger einen ICorDebugType, der den Basistyp darstellt, sofern vorhanden, der der Typ des von diesem dargestellt `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="74b81-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74b81-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74b81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="74b81-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="74b81-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` Objekt, das den Basistyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="74b81-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74b81-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74b81-107">Remarks</span></span>  
 <span data-ttu-id="74b81-108">Der Basistyp für einen Typ Nachschlagen ist nützlich, allgemeine Debuggerfunktionen, z. B. Ausgeben aller Felder eines Objekts oder die übergeordneten Klassen implementieren.</span><span class="sxs-lookup"><span data-stu-id="74b81-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b81-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74b81-109">Requirements</span></span>  
 <span data-ttu-id="74b81-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74b81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74b81-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74b81-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74b81-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74b81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74b81-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74b81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
