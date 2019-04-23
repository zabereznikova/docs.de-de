---
title: ICorDebugMergedAssemblyRecord::GetVersion-Methode
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36cf8647b3caafeaae2db3c2fd53471496e922fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109538"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="ef0a7-102">ICorDebugMergedAssemblyRecord::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="ef0a7-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="ef0a7-103">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef0a7-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef0a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef0a7-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="ef0a7-106">[out] Ein Zeiger auf die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="ef0a7-107">[out] Ein Zeiger auf die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="ef0a7-108">[out] Ein Zeiger auf die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="ef0a7-109">[out] Ein Zeiger auf die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef0a7-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef0a7-110">Remarks</span></span>  
 <span data-ttu-id="ef0a7-111">Informationen zu den Versionsnummern von Assemblys finden Sie im Thema zur <xref:System.Version>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef0a7-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef0a7-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef0a7-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef0a7-113">Requirements</span></span>  
 <span data-ttu-id="ef0a7-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef0a7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef0a7-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef0a7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef0a7-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef0a7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef0a7-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef0a7-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0a7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef0a7-118">See also</span></span>

- [<span data-ttu-id="ef0a7-119">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef0a7-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ef0a7-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ef0a7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
