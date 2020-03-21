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
ms.openlocfilehash: 7648a1b3d219ee5d2b1ddc6b26f7b65c9ac85105
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175641"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="ceb00-102">IMetaDataEmit::SetFieldRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="ceb00-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="ceb00-103">Legt einen globalen Variablenwert für die relative virtuelle Adresse des Felds fest, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ceb00-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceb00-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ceb00-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="ceb00-106">[in] Das Token für das Zielfeld.</span><span class="sxs-lookup"><span data-stu-id="ceb00-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="ceb00-107">[in] Die Adresse eines Codes oder Datenbereichs.</span><span class="sxs-lookup"><span data-stu-id="ceb00-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb00-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ceb00-108">Requirements</span></span>  
 <span data-ttu-id="ceb00-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb00-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb00-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ceb00-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ceb00-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ceb00-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ceb00-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb00-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb00-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceb00-113">See also</span></span>

- [<span data-ttu-id="ceb00-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb00-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ceb00-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceb00-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
