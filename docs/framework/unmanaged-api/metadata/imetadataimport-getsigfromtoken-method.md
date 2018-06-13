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
ms.openlocfilehash: f40fb2e94eac13211cf8ccf179904071a23f59ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447226"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="eb80a-102">IMetaDataImport::GetSigFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="eb80a-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="eb80a-103">Ruft die binäre Metadatensignatur ab, die dem angegebenen Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="eb80a-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb80a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb80a-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb80a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb80a-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="eb80a-106">[in] Das Token für die binäre Metadatensignatur zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb80a-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="eb80a-107">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Signatur.</span><span class="sxs-lookup"><span data-stu-id="eb80a-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="eb80a-108">[out] Die Größe in Bytes, der die binäre Metadatensignatur.</span><span class="sxs-lookup"><span data-stu-id="eb80a-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb80a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb80a-109">Requirements</span></span>  
 <span data-ttu-id="eb80a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb80a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb80a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb80a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb80a-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eb80a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb80a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb80a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb80a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb80a-114">See Also</span></span>  
 [<span data-ttu-id="eb80a-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb80a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="eb80a-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb80a-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
