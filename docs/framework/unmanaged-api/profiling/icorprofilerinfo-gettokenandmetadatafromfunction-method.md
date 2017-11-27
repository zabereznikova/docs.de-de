---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 585b28161814045777cf2294f78bafc3229bfae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="9ddff-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="9ddff-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="9ddff-103">Ruft das Metadatentoken und eine Instanz der Metadaten-Schnittstelle, die für die angegebene Funktion anhand des Tokens verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ddff-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ddff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ddff-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ddff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ddff-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9ddff-106">[in] Die ID der Funktion, für die das Metadatentoken und die Metadatenschnittstelle abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ddff-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="9ddff-107">[in] Die Verweis-ID der Metadatenschnittstelle zum Abrufen einer Instanz von.</span><span class="sxs-lookup"><span data-stu-id="9ddff-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="9ddff-108">[out] Ein Zeiger auf die Adresse der Instanz der Metadaten, die für die angegebene Funktion anhand des Tokens verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ddff-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="9ddff-109">[out] Ein Zeiger auf das Metadatentoken für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="9ddff-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddff-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ddff-110">Requirements</span></span>  
 <span data-ttu-id="9ddff-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ddff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddff-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ddff-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ddff-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ddff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ddff-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ddff-115">See Also</span></span>  
 [<span data-ttu-id="9ddff-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ddff-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
