---
title: IMetaDataEmit::SetMethodImplFlags-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28c0aa37bdcae2a09a4d53f920efd3ffe7117bd3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145170"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="15bab-102">IMetaDataEmit::SetMethodImplFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="15bab-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="15bab-103">Legt fest oder aktualisiert die Metadatensignatur der geerbten Methode-Implementierung, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="15bab-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15bab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15bab-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15bab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15bab-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="15bab-106">[in] Das Token für die Methode, die geändert werden.</span><span class="sxs-lookup"><span data-stu-id="15bab-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="15bab-107">[in] Eine Kombination der Werte von der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration, die Funktionen zur Implementierung der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="15bab-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15bab-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15bab-108">Requirements</span></span>  
 <span data-ttu-id="15bab-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15bab-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15bab-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15bab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15bab-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="15bab-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="15bab-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="15bab-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15bab-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15bab-113">See also</span></span>

- [<span data-ttu-id="15bab-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15bab-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="15bab-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15bab-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
