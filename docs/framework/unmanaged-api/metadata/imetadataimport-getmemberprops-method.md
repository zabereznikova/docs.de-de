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
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611409"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="695bf-102">IMetaDataImport::GetMemberProps-Methode</span><span class="sxs-lookup"><span data-stu-id="695bf-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="695bf-103">Ruft Metadateninformationen, einschließlich der Namen, die binäre Signatur und die relative virtuelle Adresse, von der <xref:System.Type> Member vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="695bf-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="695bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="695bf-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="695bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="695bf-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="695bf-106">[in] Das Token, das Element zum Abrufen der zugehörigen Metadaten für verweist.</span><span class="sxs-lookup"><span data-stu-id="695bf-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="695bf-107">[out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="695bf-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="695bf-108">[out] Der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="695bf-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="695bf-109">[in] Die Größe in Breitzeichen die `szMember` Puffer.</span><span class="sxs-lookup"><span data-stu-id="695bf-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="695bf-110">[out] Die Größe in Breitzeichen der zurückgegebene Name.</span><span class="sxs-lookup"><span data-stu-id="695bf-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="695bf-111">[out] Alle Flagwerte, die auf den Member angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="695bf-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="695bf-112">[out] Ein Zeiger auf die binäre Metadatensignatur des Elements.</span><span class="sxs-lookup"><span data-stu-id="695bf-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="695bf-113">[out] Die Größe in Bytes der `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="695bf-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="695bf-114">[out] Ein Zeiger auf die relative virtuelle Adresse des Elements.</span><span class="sxs-lookup"><span data-stu-id="695bf-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="695bf-115">[out] Alle Methodenimplementierungsflags, der dem Element zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="695bf-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="695bf-116">[out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="695bf-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="695bf-117">[out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="695bf-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="695bf-118">[out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="695bf-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="695bf-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="695bf-119">Requirements</span></span>  
 <span data-ttu-id="695bf-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="695bf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="695bf-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="695bf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="695bf-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="695bf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="695bf-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="695bf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="695bf-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="695bf-124">See also</span></span>
- [<span data-ttu-id="695bf-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="695bf-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="695bf-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="695bf-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
