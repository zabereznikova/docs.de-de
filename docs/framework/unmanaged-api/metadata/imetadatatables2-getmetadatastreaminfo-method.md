---
title: IMetaDataTables2::GetMetaDataStreamInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57fa18df1baece984a745725dba614e8c4bb1450
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471453"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="5f7e2-102">IMetaDataTables2::GetMetaDataStreamInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5f7e2-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="5f7e2-103">Ruft ab, der Name, Größe und Inhalt des Metadatenstreams am angegebenen Index.</span><span class="sxs-lookup"><span data-stu-id="5f7e2-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f7e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f7e2-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f7e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f7e2-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="5f7e2-106">[in] Der Index des angeforderten Metadatenstreams.</span><span class="sxs-lookup"><span data-stu-id="5f7e2-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="5f7e2-107">[out] Ein Zeiger auf den Namen des Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="5f7e2-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="5f7e2-108">[out] Ein Zeiger auf die Metadaten-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="5f7e2-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="5f7e2-109">[out] Die Größe in Bytes, des `ppv`.</span><span class="sxs-lookup"><span data-stu-id="5f7e2-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f7e2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f7e2-110">Requirements</span></span>  
 <span data-ttu-id="5f7e2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f7e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f7e2-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f7e2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f7e2-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5f7e2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f7e2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f7e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f7e2-115">See also</span></span>
- [<span data-ttu-id="5f7e2-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f7e2-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="5f7e2-117">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f7e2-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
