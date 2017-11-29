---
title: IMetaDataImport::GetTypeDefProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1025ffde2bd066c81c4c562c0dd86e829fc2aef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="268c0-102">IMetaDataImport::GetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="268c0-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="268c0-103">Gibt Metadateninformationen für die <xref:System.Type> durch das angegebene TypeDef-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="268c0-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="268c0-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="268c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="268c0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="268c0-106">[in] Das TypeDef-Token, das den zurückzugebenden Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="268c0-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="268c0-107">[out] Ein Puffer, der den Typnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="268c0-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="268c0-108">[in] Die Größe in Breitzeichen `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="268c0-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="268c0-109">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="268c0-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="268c0-110">[out] Ein Zeiger auf die Flags, die die Typdefinition ändern.</span><span class="sxs-lookup"><span data-stu-id="268c0-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="268c0-111">Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="268c0-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="268c0-112">[out] Eine TypeDef oder TypeRef-Token Metadatentoken, das den Basistyp des angeforderten Typs darstellt.</span><span class="sxs-lookup"><span data-stu-id="268c0-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268c0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="268c0-113">Requirements</span></span>  
 <span data-ttu-id="268c0-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="268c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="268c0-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="268c0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="268c0-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="268c0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="268c0-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="268c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268c0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="268c0-118">See Also</span></span>  
 [<span data-ttu-id="268c0-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268c0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="268c0-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268c0-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
