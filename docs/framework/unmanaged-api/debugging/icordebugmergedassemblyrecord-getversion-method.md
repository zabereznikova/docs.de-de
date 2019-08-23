---
title: ICorDebugMergedAssemblyRecord::GetVersion-Methode
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d9133ab1b7d3985d3a383bb36dcbea315548c00
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939929"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="fcd13-102">ICorDebugMergedAssemblyRecord::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="fcd13-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="fcd13-103">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="fcd13-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcd13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcd13-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="fcd13-106">[out] Ein Zeiger auf die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="fcd13-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="fcd13-107">[out] Ein Zeiger auf die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="fcd13-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="fcd13-108">[out] Ein Zeiger auf die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="fcd13-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="fcd13-109">[out] Ein Zeiger auf die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="fcd13-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd13-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcd13-110">Remarks</span></span>  
 <span data-ttu-id="fcd13-111">Informationen zu den Versionsnummern von Assemblys finden Sie im Thema zur <xref:System.Version>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fcd13-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcd13-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fcd13-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd13-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcd13-113">Requirements</span></span>  
 <span data-ttu-id="fcd13-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd13-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd13-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="fcd13-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd13-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd13-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd13-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd13-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd13-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcd13-118">See also</span></span>

- [<span data-ttu-id="fcd13-119">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcd13-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="fcd13-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcd13-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
