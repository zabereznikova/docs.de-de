---
title: IMetaDataImport::FindTypeRef-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3321f8ea1897f807a06d5c9a812fded2fd7f6365
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="f6025-102">IMetaDataImport::FindTypeRef-Methode</span><span class="sxs-lookup"><span data-stu-id="f6025-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="f6025-103">Ruft einen Zeiger auf das TypeRef-token für die <xref:System.Type> Referenz, die sich auf den angegebenen Bereich und den angegebenen Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="f6025-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6025-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6025-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6025-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6025-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="f6025-106">[in] Ein ModuleRef, AssemblyRef oder TypeRef-Token, das das Modul, Assembly oder der Typ gibt an, ist in dem der Referenztyp definiert.</span><span class="sxs-lookup"><span data-stu-id="f6025-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="f6025-107">[in] Der Name des Verweises zu suchenden Typs.</span><span class="sxs-lookup"><span data-stu-id="f6025-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="f6025-108">[out] Ein Zeiger auf das übereinstimmende TypeRef-Token.</span><span class="sxs-lookup"><span data-stu-id="f6025-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6025-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6025-109">Requirements</span></span>  
 <span data-ttu-id="f6025-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6025-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6025-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6025-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6025-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6025-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6025-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6025-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6025-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6025-114">See Also</span></span>  
 [<span data-ttu-id="f6025-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6025-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f6025-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6025-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
