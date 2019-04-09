---
title: IMetaDataTables::GetBlob-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: babe098b16729cfcd41b48075a49b9ae9be7dfdc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117182"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="6fa5d-102">IMetaDataTables::GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="6fa5d-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="6fa5d-103">Ruft einen Zeiger auf das binary large Object (BLOB) am Index angegebene Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="6fa5d-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fa5d-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa5d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fa5d-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="6fa5d-106">[in] Die Speicheradresse, von dem abzurufenden `ppData`.</span><span class="sxs-lookup"><span data-stu-id="6fa5d-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="6fa5d-107">[out] Ein Zeiger auf die Größe in Bytes, des `ppData`.</span><span class="sxs-lookup"><span data-stu-id="6fa5d-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="6fa5d-108">[out] Ein Zeiger auf einen Zeiger auf die binären Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6fa5d-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa5d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fa5d-109">Requirements</span></span>  
 <span data-ttu-id="6fa5d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa5d-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6fa5d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fa5d-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6fa5d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6fa5d-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6fa5d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fa5d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fa5d-114">See also</span></span>

- [<span data-ttu-id="6fa5d-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fa5d-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6fa5d-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fa5d-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
