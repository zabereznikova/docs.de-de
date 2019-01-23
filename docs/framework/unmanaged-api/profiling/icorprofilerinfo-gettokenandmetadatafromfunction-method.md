---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0561f76c70da603d50b96ce5b5162efac4eff2de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492976"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="d3ac9-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="d3ac9-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="d3ac9-103">Ruft das Metadatentoken und eine Instanz der Metadaten-Schnittstelle, die für die angegebene Funktion anhand des Tokens verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d3ac9-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ac9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3ac9-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3ac9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3ac9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d3ac9-106">[in] Die ID der Funktion für die das Metadatentoken und die Metadaten-Schnittstelle abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3ac9-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="d3ac9-107">[in] Die Referenz-ID der Metadatenschnittstelle, von der Instanz abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d3ac9-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="d3ac9-108">[out] Ein Zeiger auf die Adresse der Instanz der Schnittstelle, die für die angegebene Funktion anhand des Tokens verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d3ac9-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="d3ac9-109">[out] Ein Zeiger auf das Metadatentoken für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="d3ac9-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ac9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3ac9-110">Requirements</span></span>  
 <span data-ttu-id="d3ac9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ac9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ac9-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3ac9-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3ac9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3ac9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3ac9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ac9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ac9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3ac9-115">See also</span></span>
- [<span data-ttu-id="d3ac9-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3ac9-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
