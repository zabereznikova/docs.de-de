---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ef8d1c47275d3cbd69c1516b788b950f8535513
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737714"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="2c5a2-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="2c5a2-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="2c5a2-103">Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne, basierend auf ihren Schnittstellenbezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c5a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c5a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c5a2-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="2c5a2-106">[in] Die Anzahl der erforderlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="2c5a2-107">[in] Ein Zeiger auf ein Array mit den Schnittstellenbezeichner, der für die verwaltete Darstellungen von der Windows-Runtime-Typen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="2c5a2-108">[out] Ein Zeiger auf die Adresse eines Objekts der "ICorDebugTypeEnum"-Schnittstelle, die Enumeration der zwischengespeicherten verwaltete Darstellungen von der Windows-Runtime-Typen ermöglicht abgerufen, die basierend auf den Schnittstellenbezeichner in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c5a2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c5a2-109">Remarks</span></span>  
 <span data-ttu-id="2c5a2-110">Fällt die Methode zum Abrufen von Informationen für eine bestimmte Schnittstelle-ID, weist der entsprechende Eintrag in der Auflistung "ICorDebugTypeEnum" einen Typ von `ELEMENT_TYPE_END` nach Fehlern aufgrund von Datenproblemen abrufen, oder `ELEMENT_TYPE_VOID` für unbekannte-Schnittstelle Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="2c5a2-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5a2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c5a2-111">Requirements</span></span>  
 <span data-ttu-id="2c5a2-112">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="2c5a2-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2c5a2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c5a2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c5a2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c5a2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c5a2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c5a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5a2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c5a2-116">See also</span></span>

- [<span data-ttu-id="2c5a2-117">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c5a2-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
