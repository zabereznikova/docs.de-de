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
ms.openlocfilehash: 8f6b5582b96dfc83eed482def2c4c4abfeb33a4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042990"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="75395-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="75395-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="75395-103">Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.</span><span class="sxs-lookup"><span data-stu-id="75395-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75395-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75395-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75395-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75395-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="75395-106">[in] Der beschreibbare Stream zu speichern.</span><span class="sxs-lookup"><span data-stu-id="75395-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="75395-107">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="75395-107">[in] Reserved.</span></span> <span data-ttu-id="75395-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="75395-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75395-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75395-109">Requirements</span></span>  
 <span data-ttu-id="75395-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75395-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75395-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75395-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75395-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="75395-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75395-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75395-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75395-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75395-114">See also</span></span>

- [<span data-ttu-id="75395-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75395-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="75395-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75395-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
