---
title: IMetaDataEmit::SaveToStream-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 515e925c9b086823450b73cfbb558d0409b4948a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575998"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="c6366-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="c6366-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="c6366-103">Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.</span><span class="sxs-lookup"><span data-stu-id="c6366-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6366-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6366-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6366-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6366-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="c6366-106">[in] Der beschreibbare Stream zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c6366-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c6366-107">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="c6366-107">[in] Reserved.</span></span> <span data-ttu-id="c6366-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="c6366-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6366-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6366-109">Requirements</span></span>  
 <span data-ttu-id="c6366-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6366-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6366-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6366-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6366-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c6366-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6366-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6366-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6366-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6366-114">See also</span></span>
- [<span data-ttu-id="c6366-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6366-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c6366-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6366-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
