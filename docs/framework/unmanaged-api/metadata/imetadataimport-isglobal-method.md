---
title: IMetaDataImport::IsGlobal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b956ac1717ffcb73e819e985450249754f80af2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136161"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="6ff8a-102">IMetaDataImport::IsGlobal-Methode</span><span class="sxs-lookup"><span data-stu-id="6ff8a-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="6ff8a-103">Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.</span><span class="sxs-lookup"><span data-stu-id="6ff8a-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ff8a-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ff8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ff8a-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="6ff8a-106">[in] Ein Metadatentoken, das einen Typ, ein Feld oder Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="6ff8a-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="6ff8a-107">[out] 1, wenn hat das Objekt einen globalen Gültigkeitsbereich; andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6ff8a-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ff8a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ff8a-108">Requirements</span></span>  
 <span data-ttu-id="6ff8a-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ff8a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ff8a-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ff8a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ff8a-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6ff8a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ff8a-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6ff8a-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ff8a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ff8a-113">See also</span></span>

- [<span data-ttu-id="6ff8a-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ff8a-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6ff8a-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ff8a-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
