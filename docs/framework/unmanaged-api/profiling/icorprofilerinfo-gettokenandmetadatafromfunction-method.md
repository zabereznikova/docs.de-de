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
ms.openlocfilehash: 8e03eefc3758347389be4af6d53921480ee40263
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724077"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="3ef4d-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="3ef4d-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>

<span data-ttu-id="3ef4d-103">Ruft das Metadatentoken und eine Instanz der Metadatenschnittstelle ab, die für das Token für die angegebene Funktion verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3ef4d-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ef4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ef4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ef4d-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="3ef4d-106">in Die ID der Funktion, für die das Metadatentoken und die Metadatenschnittstelle zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="3ef4d-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="3ef4d-107">in Die Verweis-ID der Metadatenschnittstelle, von der die Instanz von abgeraten werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ef4d-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="3ef4d-108">vorgenommen Ein Zeiger auf die Adresse der Instanz der Metadatenschnittstelle, die für das Token für die angegebene Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ef4d-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="3ef4d-109">vorgenommen Ein Zeiger auf das Metadatentoken für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="3ef4d-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef4d-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ef4d-110">Requirements</span></span>  

 <span data-ttu-id="3ef4d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ef4d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ef4d-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ef4d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ef4d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ef4d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ef4d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ef4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef4d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ef4d-115">See also</span></span>

- [<span data-ttu-id="3ef4d-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ef4d-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
