---
title: IMetaDataImport::ResetEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163877"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="8ed17-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="8ed17-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="8ed17-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="8ed17-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed17-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ed17-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ed17-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ed17-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8ed17-106">[in] Der Enumerator zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="8ed17-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="8ed17-107">[in] Die neue Position, an dem den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="8ed17-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ed17-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ed17-108">Requirements</span></span>  
 <span data-ttu-id="8ed17-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ed17-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ed17-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ed17-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ed17-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ed17-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8ed17-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8ed17-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ed17-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ed17-113">See also</span></span>

- [<span data-ttu-id="8ed17-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ed17-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8ed17-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ed17-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
