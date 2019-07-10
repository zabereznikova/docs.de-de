---
title: IMetaDataImport::GetNestedClassProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7dd59c1e0e8b28c557910da3fd9c6489370cc62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778947"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="bdc4d-102">IMetaDataImport::GetNestedClassProps-Methode</span><span class="sxs-lookup"><span data-stu-id="bdc4d-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="bdc4d-103">Ruft Sie die TypeDef-token für das übergeordnete Element <xref:System.Type> des angegebenen geschachtelten Typ.</span><span class="sxs-lookup"><span data-stu-id="bdc4d-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdc4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdc4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bdc4d-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="bdc4d-106">[in] Ein TypeDef-token, die <xref:System.Type> zurückgegeben von der übergeordneten Klasse für token.</span><span class="sxs-lookup"><span data-stu-id="bdc4d-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="bdc4d-107">[out] Ein Zeiger auf das TypeDef-Token für die <xref:System.Type> , `tdNestedClass` in geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="bdc4d-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc4d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdc4d-108">Requirements</span></span>  
 <span data-ttu-id="bdc4d-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdc4d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc4d-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bdc4d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdc4d-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bdc4d-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdc4d-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc4d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc4d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdc4d-113">See also</span></span>

- [<span data-ttu-id="bdc4d-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdc4d-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bdc4d-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdc4d-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
