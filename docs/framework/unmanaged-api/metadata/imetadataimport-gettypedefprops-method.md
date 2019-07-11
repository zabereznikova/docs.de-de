---
title: IMetaDataImport::GetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77f72fb7eb7b0542dc9a3179811a78b189d6b3b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778840"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="94bc2-102">IMetaDataImport::GetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="94bc2-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="94bc2-103">Gibt Metadateninformationen für die <xref:System.Type> durch das angegebene TypeDef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="94bc2-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94bc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94bc2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94bc2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94bc2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="94bc2-106">[in] Die TypeDef-Token, das die den zurückzugebenden Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="94bc2-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="94bc2-107">[out] Ein Puffer, die den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="94bc2-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="94bc2-108">[in] Die Größe in Breitzeichen `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="94bc2-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="94bc2-109">[out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="94bc2-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="94bc2-110">[out] Ein Zeiger auf Flags, die die Typdefinition ändern.</span><span class="sxs-lookup"><span data-stu-id="94bc2-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="94bc2-111">Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="94bc2-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="94bc2-112">[out] Eine TypeDef oder TypeRef-Metadaten-Token, das den Basistyp des angeforderten Typs darstellt.</span><span class="sxs-lookup"><span data-stu-id="94bc2-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94bc2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94bc2-113">Requirements</span></span>  
 <span data-ttu-id="94bc2-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94bc2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94bc2-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94bc2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94bc2-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94bc2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94bc2-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94bc2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bc2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94bc2-118">See also</span></span>

- [<span data-ttu-id="94bc2-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94bc2-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="94bc2-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94bc2-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
