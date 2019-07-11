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
ms.openlocfilehash: 7f182dad17e28cc5d19393bb4e13d747e34249fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782481"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="c7715-102">IMetaDataImport::FindTypeDefByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c7715-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="c7715-103">Ruft einen Zeiger auf die Metadaten der TypeDef-token für die <xref:System.Type> mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="c7715-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7715-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7715-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7715-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7715-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="c7715-106">[in] Der Name des Typs für die die TypeDef-token abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7715-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="c7715-107">[in] Eine TypeDef oder TypeRef-Token, die die einschließende Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7715-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="c7715-108">Wenn die Eingabe zur Suche nach nicht um eine geschachtelte Klasse ist, wird dieser Wert auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7715-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="c7715-109">[out] Ein Zeiger auf das passende TypeDef-Token.</span><span class="sxs-lookup"><span data-stu-id="c7715-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7715-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7715-110">Requirements</span></span>  
 <span data-ttu-id="c7715-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7715-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7715-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c7715-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7715-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c7715-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7715-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7715-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7715-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7715-115">See also</span></span>

- [<span data-ttu-id="c7715-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7715-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c7715-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7715-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
