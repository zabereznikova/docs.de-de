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
ms.openlocfilehash: 5aceed6fa662f090dfe360ddca51da1381b12a2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631494"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="da186-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="da186-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="da186-103">Ruft einen Enumerator ab, für die Zwischenspeicherung [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne auf der Grundlage von deren Schnittstellenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="da186-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da186-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da186-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da186-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="da186-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="da186-106">[in] Die Anzahl der erforderlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="da186-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="da186-107">[in] Ein Zeiger auf ein Array, das die verwaltete Darstellung der entsprechenden Schnittstellenbezeichner enthält den [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="da186-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="da186-108">[out] Ein Zeiger auf die Adresse einer "ICorDebugTypeEnum"-Schnittstellenobjekts, das ermöglicht die Enumeration, der die zwischengespeicherten verwaltete Darstellungen der [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen abgerufen, die basierend auf den Schnittstellenbezeichner in `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="da186-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da186-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da186-109">Remarks</span></span>  
 <span data-ttu-id="da186-110">Fällt die Methode zum Abrufen von Informationen für eine bestimmte Schnittstelle-ID, weist der entsprechende Eintrag in der Auflistung "ICorDebugTypeEnum" einen Typ von `ELEMENT_TYPE_END` nach Fehlern aufgrund von Datenproblemen abrufen, oder `ELEMENT_TYPE_VOID` für unbekannte-Schnittstelle Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="da186-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da186-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da186-111">Requirements</span></span>  
 <span data-ttu-id="da186-112">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da186-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="da186-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da186-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da186-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da186-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da186-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da186-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da186-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da186-116">See also</span></span>
- [<span data-ttu-id="da186-117">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da186-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
