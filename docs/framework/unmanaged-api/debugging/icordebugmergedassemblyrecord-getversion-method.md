---
title: ICorDebugMergedAssemblyRecord::GetVersion-Methode
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 7352a77fc8f41124d7e6c78a3dfc6ccd6d3a94aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710505"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="bc3b2-102">ICorDebugMergedAssemblyRecord::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="bc3b2-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>

<span data-ttu-id="bc3b2-103">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc3b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc3b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc3b2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc3b2-105">Parameters</span></span>  

 `pMajor`  
 <span data-ttu-id="bc3b2-106">[out] Ein Zeiger auf die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="bc3b2-107">[out] Ein Zeiger auf die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="bc3b2-108">[out] Ein Zeiger auf die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="bc3b2-109">[out] Ein Zeiger auf die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc3b2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc3b2-110">Remarks</span></span>  

 <span data-ttu-id="bc3b2-111">Informationen zu den Versionsnummern von Assemblys finden Sie im Thema zur <xref:System.Version>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc3b2-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc3b2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc3b2-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bc3b2-113">Requirements</span></span>  

 <span data-ttu-id="bc3b2-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3b2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc3b2-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc3b2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc3b2-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc3b2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc3b2-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3b2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3b2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc3b2-118">See also</span></span>

- [<span data-ttu-id="bc3b2-119">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc3b2-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bc3b2-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc3b2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
