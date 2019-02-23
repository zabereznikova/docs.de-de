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
ms.openlocfilehash: 40631a15bd07b5aa54488e5d3b99cee751e2e0bd
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748335"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="de1a8-102">IMetaDataImport::GetMemberProps-Methode</span><span class="sxs-lookup"><span data-stu-id="de1a8-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="de1a8-103">Ruft ab, in den Metadaten für eine angegebenen Member-Definition, einschließlich Name, binäre Signatur und relative virtuelle Adresse des gespeicherten Informationen dem <xref:System.Type> Member vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="de1a8-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="de1a8-104">Dies ist eine einfache Hilfsmethode: Wenn *mb* MethodDef, dann ist **GetMethodProps** aufgerufen, wenn *mb* ist ein FieldDef, **GetFieldProps** wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="de1a8-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="de1a8-105">Finden Sie unter diesen anderen Methoden für Details.</span><span class="sxs-lookup"><span data-stu-id="de1a8-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="de1a8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="de1a8-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="de1a8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="de1a8-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="de1a8-108">[in] Das Token, das Element zum Abrufen der zugehörigen Metadaten für verweist.</span><span class="sxs-lookup"><span data-stu-id="de1a8-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="de1a8-109">[out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="de1a8-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="de1a8-110">[out] Der Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="de1a8-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="de1a8-111">[in] Die Größe in Breitzeichen die `szMember` Puffer.</span><span class="sxs-lookup"><span data-stu-id="de1a8-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="de1a8-112">[out] Die Größe in Breitzeichen der zurückgegebene Name.</span><span class="sxs-lookup"><span data-stu-id="de1a8-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="de1a8-113">[out] Alle Flagwerte, die auf den Member angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="de1a8-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="de1a8-114">[out] Ein Zeiger auf die binäre Metadatensignatur des Elements.</span><span class="sxs-lookup"><span data-stu-id="de1a8-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="de1a8-115">[out] Die Größe in Bytes der `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="de1a8-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="de1a8-116">[out] Ein Zeiger auf die relative virtuelle Adresse des Elements.</span><span class="sxs-lookup"><span data-stu-id="de1a8-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="de1a8-117">[out] Alle Methodenimplementierungsflags, der dem Element zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="de1a8-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="de1a8-118">[out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="de1a8-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="de1a8-119">Es ist eines der `ELEMENT_TYPE_*` Werte.</span><span class="sxs-lookup"><span data-stu-id="de1a8-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="de1a8-120">[out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de1a8-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="de1a8-121">[out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de1a8-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de1a8-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de1a8-122">Requirements</span></span>  
 <span data-ttu-id="de1a8-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de1a8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de1a8-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de1a8-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de1a8-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="de1a8-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de1a8-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de1a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de1a8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de1a8-127">See also</span></span>
- [<span data-ttu-id="de1a8-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de1a8-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="de1a8-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de1a8-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
