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
ms.openlocfilehash: 8b259636a8bd28abd3bba12c4a05dda3c13557e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784892"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="abf8f-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="abf8f-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="abf8f-103">Ruft einen Enumerator für zwischengespeicherte Windows-Runtime Typen in einer Anwendungsdomäne auf der Grundlage ihrer Schnittstellen Bezeichner ab.</span><span class="sxs-lookup"><span data-stu-id="abf8f-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="abf8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abf8f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="abf8f-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="abf8f-106">in Die Anzahl der erforderlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="abf8f-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="abf8f-107">in Ein Zeiger auf ein Array, das die Schnittstellen Bezeichner enthält, die den verwalteten Darstellungen der Windows-Runtime Typen entsprechen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="abf8f-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="abf8f-108">vorgenommen Ein Zeiger auf die Adresse eines icorentbugtypeenum-Schnittstellen Objekts, das die Enumeration der zwischengespeicherten verwalteten Darstellungen der Windows-Runtime abgerufenen Typen basierend auf den Schnittstellen Bezeichners in `iidsToResolve`ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="abf8f-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abf8f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abf8f-109">Remarks</span></span>  
 <span data-ttu-id="abf8f-110">Wenn die Methode keine Informationen für einen bestimmten Schnittstellen Bezeichner abrufen kann, weist der entsprechende Eintrag in der ICorDebugTypeEnum-Auflistung aufgrund von Datenabruf Problemen einen Typ von `ELEMENT_TYPE_END` oder `ELEMENT_TYPE_VOID` für unbekannte Schnittstellen Bezeichner auf.</span><span class="sxs-lookup"><span data-stu-id="abf8f-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf8f-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="abf8f-111">Requirements</span></span>  
 <span data-ttu-id="abf8f-112">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="abf8f-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="abf8f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abf8f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abf8f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abf8f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abf8f-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf8f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abf8f-116">See also</span></span>

- [<span data-ttu-id="abf8f-117">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abf8f-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
