---
title: ICorProfilerInfo::GetModuleMetaData-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 540ed6f1f84f096563aa94798090c3511d6db5d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="c146d-102">ICorProfilerInfo::GetModuleMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="c146d-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="c146d-103">Ruft eine Instanz der Metadaten-Schnittstelle, die das angegebene Modul zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c146d-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c146d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c146d-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c146d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c146d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c146d-106">[in] Die ID des Moduls, der die Schnittstelleninstanz zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c146d-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="c146d-107">[in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration, der den Modus zum Öffnen von Manifestdateien angibt.</span><span class="sxs-lookup"><span data-stu-id="c146d-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="c146d-108">Nur die `ofRead`, `ofWrite` und `ofNoTransform` Bits sind gültig.</span><span class="sxs-lookup"><span data-stu-id="c146d-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="c146d-109">[in] Der Verweis-ID (GUID) der Metadatenschnittstelle, deren Instanz abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c146d-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="c146d-110">Finden Sie unter [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) eine Liste der Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="c146d-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="c146d-111">[out] Ein Zeiger auf die Adresse der Instanz der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="c146d-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c146d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c146d-112">Remarks</span></span>  
 <span data-ttu-id="c146d-113">Sie Fragen sich vielleicht für die Metadaten in Lese-/Schreibmodus geöffnet werden, aber dies führt zu einer langsameren Metadaten Ausführung des Programms, da Änderungen kann nicht die Metadaten wie vom Compiler optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="c146d-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="c146d-114">Einige Module (z. B. Ressourcenmodule) verfügen über keine Metadaten.</span><span class="sxs-lookup"><span data-stu-id="c146d-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="c146d-115">In diesen Fällen `GetModuleMetaData` zurück einen HRESULT-Wert von "S_FALSE" und ein NULL-Wert in *`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="c146d-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c146d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c146d-116">Requirements</span></span>  
 <span data-ttu-id="c146d-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c146d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c146d-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c146d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c146d-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c146d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c146d-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c146d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c146d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c146d-121">See Also</span></span>  
 [<span data-ttu-id="c146d-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c146d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
