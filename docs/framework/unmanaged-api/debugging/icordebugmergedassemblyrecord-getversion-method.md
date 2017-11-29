---
title: ICorDebugMergedAssemblyRecord::GetVersion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68fa2b1b7502f13876c6e613f012a0c78ab7c5d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="e2586-102">ICorDebugMergedAssemblyRecord::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="e2586-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="e2586-103">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="e2586-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2586-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2586-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2586-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2586-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="e2586-106">[out] Ein Zeiger auf die Hauptversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2586-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="e2586-107">[out] Ein Zeiger auf die Nebenversionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2586-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="e2586-108">[out] Ein Zeiger auf die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="e2586-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="e2586-109">[out] Ein Zeiger auf die Revisionsnummer.</span><span class="sxs-lookup"><span data-stu-id="e2586-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2586-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2586-110">Remarks</span></span>  
 <span data-ttu-id="e2586-111">Informationen zu den Versionsnummern von Assemblys finden Sie im Thema zur <xref:System.Version>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e2586-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2586-112">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2586-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2586-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2586-113">Requirements</span></span>  
 <span data-ttu-id="e2586-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2586-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2586-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2586-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2586-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2586-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2586-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2586-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2586-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2586-118">See Also</span></span>  
 [<span data-ttu-id="e2586-119">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2586-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="e2586-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2586-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
