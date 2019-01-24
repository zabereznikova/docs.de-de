---
title: IMetaDataImport::FindTypeDefByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b6040f21bb530ce775fc79e33b97eb14870c04f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578813"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="68362-102">IMetaDataImport::FindTypeDefByName-Methode</span><span class="sxs-lookup"><span data-stu-id="68362-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="68362-103">Ruft einen Zeiger auf die Metadaten der TypeDef-token für die <xref:System.Type> mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="68362-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68362-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68362-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68362-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68362-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="68362-106">[in] Der Name des Typs für die die TypeDef-token abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="68362-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="68362-107">[in] Eine TypeDef oder TypeRef-Token, die die einschließende Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="68362-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="68362-108">Wenn die Eingabe zur Suche nach nicht um eine geschachtelte Klasse ist, wird dieser Wert auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68362-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="68362-109">[out] Ein Zeiger auf das passende TypeDef-Token.</span><span class="sxs-lookup"><span data-stu-id="68362-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68362-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68362-110">Requirements</span></span>  
 <span data-ttu-id="68362-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68362-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68362-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="68362-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68362-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68362-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68362-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68362-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68362-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68362-115">See also</span></span>
- [<span data-ttu-id="68362-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68362-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="68362-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68362-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
