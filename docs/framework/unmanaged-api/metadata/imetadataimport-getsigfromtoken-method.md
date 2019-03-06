---
title: IMetaDataImport::GetSigFromToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 292ab8684f20c7ec5dcb87784c0ffff7416e8880
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476346"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="3f38c-102">IMetaDataImport::GetSigFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="3f38c-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="3f38c-103">Ruft die binäre Metadatensignatur ab, die dem angegebenen Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3f38c-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f38c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f38c-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f38c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f38c-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="3f38c-106">[in] Das Token für die binäre Metadatensignatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f38c-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="3f38c-107">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Signatur.</span><span class="sxs-lookup"><span data-stu-id="3f38c-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="3f38c-108">[out] Die Größe in Bytes, der die binäre Metadatensignatur.</span><span class="sxs-lookup"><span data-stu-id="3f38c-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f38c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f38c-109">Requirements</span></span>  
 <span data-ttu-id="3f38c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f38c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f38c-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f38c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f38c-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3f38c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f38c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f38c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f38c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f38c-114">See also</span></span>
- [<span data-ttu-id="3f38c-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f38c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3f38c-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f38c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
