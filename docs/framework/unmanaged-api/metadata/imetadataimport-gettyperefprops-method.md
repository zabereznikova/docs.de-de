---
title: IMetaDataImport::GetTypeRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 191a6e4fcfe340ed43e85a9aa90f8a2ec0931730
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671654"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="f0df9-102">IMetaDataImport::GetTypeRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f0df9-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="f0df9-103">Ruft ab, die zugeordneten Metadaten den <xref:System.Type> durch das angegebene TypeRef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f0df9-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0df9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0df9-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0df9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0df9-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="f0df9-106">[in] Die TypeRef-Token, das die den zurückzugebenden Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0df9-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="f0df9-107">[out] Ein Zeiger auf den Bereich, in dem der Verweis erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="f0df9-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="f0df9-108">Dieser Wert ist ein AssemblyRef oder ModuleRef-Token.</span><span class="sxs-lookup"><span data-stu-id="f0df9-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="f0df9-109">[out] Ein Puffer, die den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="f0df9-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f0df9-110">[in] Die angeforderte Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="f0df9-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f0df9-111">[out] Die zurückgegebene Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="f0df9-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0df9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0df9-112">Requirements</span></span>  
 <span data-ttu-id="f0df9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0df9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0df9-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f0df9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0df9-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0df9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0df9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0df9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0df9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0df9-117">See also</span></span>
- [<span data-ttu-id="f0df9-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0df9-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f0df9-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0df9-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
