---
title: IMetaDataImport::FindTypeRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acc006894f05536ed76bac60b0fde9277a460813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199023"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="ab42c-102">IMetaDataImport::FindTypeRef-Methode</span><span class="sxs-lookup"><span data-stu-id="ab42c-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="ab42c-103">Ruft einen Zeiger auf das TypeRef-token für die <xref:System.Type> Referenz, die sich in den angegebenen Bereich und den angegebenen Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ab42c-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab42c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab42c-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab42c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab42c-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="ab42c-106">[in] Ein ModuleRef, AssemblyRef oder TypeRef-Token, das das Modul, Assembly oder der Typ gibt an, wird in dem auf den Typ verweisen definiert.</span><span class="sxs-lookup"><span data-stu-id="ab42c-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="ab42c-107">[in] Der Name des zu suchenden Typverweises.</span><span class="sxs-lookup"><span data-stu-id="ab42c-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ab42c-108">[out] Ein Zeiger auf das entsprechende TypeRef-Token.</span><span class="sxs-lookup"><span data-stu-id="ab42c-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab42c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab42c-109">Requirements</span></span>  
 <span data-ttu-id="ab42c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab42c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab42c-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab42c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab42c-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ab42c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ab42c-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ab42c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab42c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab42c-114">See also</span></span>

- [<span data-ttu-id="ab42c-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab42c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ab42c-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab42c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
