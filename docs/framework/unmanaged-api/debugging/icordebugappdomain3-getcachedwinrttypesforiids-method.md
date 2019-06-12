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
ms.openlocfilehash: 95c84f7f40db0096b26ec448f8f229cdbfe3afb1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025906"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="bb69e-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="bb69e-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="bb69e-103">Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne, basierend auf ihren Schnittstellenbezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="bb69e-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb69e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb69e-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb69e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb69e-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="bb69e-106">[in] Die Anzahl der erforderlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="bb69e-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="bb69e-107">[in] Ein Zeiger auf ein Array mit den Schnittstellenbezeichner, der für die verwaltete Darstellungen von der Windows-Runtime-Typen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb69e-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="bb69e-108">[out] Ein Zeiger auf die Adresse eines Objekts der "ICorDebugTypeEnum"-Schnittstelle, die Enumeration der zwischengespeicherten verwaltete Darstellungen von der Windows-Runtime-Typen ermöglicht abgerufen, die basierend auf den Schnittstellenbezeichner in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="bb69e-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb69e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb69e-109">Remarks</span></span>  
 <span data-ttu-id="bb69e-110">Fällt die Methode zum Abrufen von Informationen für eine bestimmte Schnittstelle-ID, weist der entsprechende Eintrag in der Auflistung "ICorDebugTypeEnum" einen Typ von `ELEMENT_TYPE_END` nach Fehlern aufgrund von Datenproblemen abrufen, oder `ELEMENT_TYPE_VOID` für unbekannte-Schnittstelle Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="bb69e-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb69e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb69e-111">Requirements</span></span>  
 <span data-ttu-id="bb69e-112">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="bb69e-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="bb69e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb69e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb69e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb69e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb69e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb69e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb69e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb69e-116">See also</span></span>

- [<span data-ttu-id="bb69e-117">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb69e-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
