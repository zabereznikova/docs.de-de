---
title: IMetaDataEmit::SetFieldRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181674"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="dfab5-102">IMetaDataEmit::SetFieldRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="dfab5-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="dfab5-103">Legt einen Wert der globalen Variablen für die relative virtuelle Adresse des Felds auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dfab5-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfab5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfab5-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfab5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfab5-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="dfab5-106">[in] Das Token für das Feld "Ziel".</span><span class="sxs-lookup"><span data-stu-id="dfab5-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="dfab5-107">[in] Die Adresse eines Bereichs Code- oder Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="dfab5-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfab5-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfab5-108">Requirements</span></span>  
 <span data-ttu-id="dfab5-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfab5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfab5-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dfab5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfab5-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="dfab5-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dfab5-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="dfab5-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfab5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfab5-113">See also</span></span>

- [<span data-ttu-id="dfab5-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfab5-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dfab5-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfab5-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
