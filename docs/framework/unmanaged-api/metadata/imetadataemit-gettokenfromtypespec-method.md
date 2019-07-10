---
title: IMetaDataEmit::GetTokenFromTypeSpec-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85b0edc81a9a861a3eed6a7bc3ffc1ed1db37403
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770737"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="bb884-102">IMetaDataEmit::GetTokenFromTypeSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="bb884-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="bb884-103">Ruft Metadaten für den Typ mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="bb884-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb884-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb884-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb884-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb884-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="bb884-106">[in] Die Signatur, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb884-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="bb884-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="bb884-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="bb884-108">[out] Die `mdTypeSpec` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="bb884-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb884-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb884-109">Requirements</span></span>  
 <span data-ttu-id="bb884-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb884-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb884-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb884-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb884-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bb884-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb884-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb884-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb884-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb884-114">See also</span></span>

- [<span data-ttu-id="bb884-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb884-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bb884-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb884-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
