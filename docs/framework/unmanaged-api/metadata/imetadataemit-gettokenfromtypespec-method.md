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
ms.openlocfilehash: ff240a80d2910dcb050cc022257c6eba166bbdc5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465932"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="d2017-102">IMetaDataEmit::GetTokenFromTypeSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="d2017-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="d2017-103">Ruft Metadaten für den Typ mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="d2017-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2017-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2017-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2017-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2017-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="d2017-106">[in] Die Signatur, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2017-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="d2017-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="d2017-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="d2017-108">[out] Die `mdTypeSpec` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="d2017-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2017-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2017-109">Requirements</span></span>  
 <span data-ttu-id="d2017-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2017-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2017-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2017-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2017-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d2017-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2017-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2017-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2017-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2017-114">See also</span></span>
- [<span data-ttu-id="d2017-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2017-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d2017-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2017-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
