---
title: IMetaDataImport::GetMemberProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93763da2afbbdb1e738c802ba172e9f16e5f7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448457"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="318dc-102">IMetaDataImport::GetMemberProps-Methode</span><span class="sxs-lookup"><span data-stu-id="318dc-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="318dc-103">Ruft Metadateninformationen, einschließlich Name, binäre Signatur und relative virtuelle Adresse, von der <xref:System.Type> Member auf, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="318dc-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="318dc-104">Syntax</span></span>  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="318dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="318dc-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="318dc-106">[in] Das Token, das Element, um die zugehörigen Metadaten für erhalten verweist.</span><span class="sxs-lookup"><span data-stu-id="318dc-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="318dc-107">[out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="318dc-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="318dc-108">[out] Der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="318dc-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="318dc-109">[in] Die Größe in Breitzeichen der `szMember` Puffer.</span><span class="sxs-lookup"><span data-stu-id="318dc-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="318dc-110">[out] Die Größe in Breitzeichen mit den zurückgegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="318dc-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="318dc-111">[out] Alle Flagwerte, die auf das Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="318dc-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="318dc-112">[out] Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="318dc-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="318dc-113">[out] Die Größe in Bytes des `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="318dc-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="318dc-114">[out] Ein Zeiger auf die relative virtuelle Adresse des Elements.</span><span class="sxs-lookup"><span data-stu-id="318dc-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="318dc-115">[out] Alle Methodenimplementierungsflags, die dem Element zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="318dc-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="318dc-116">[out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="318dc-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="318dc-117">[out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="318dc-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="318dc-118">[out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="318dc-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="318dc-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="318dc-119">Requirements</span></span>  
 <span data-ttu-id="318dc-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="318dc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318dc-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="318dc-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="318dc-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="318dc-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="318dc-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="318dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318dc-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="318dc-124">See Also</span></span>  
 [<span data-ttu-id="318dc-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="318dc-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="318dc-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="318dc-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
