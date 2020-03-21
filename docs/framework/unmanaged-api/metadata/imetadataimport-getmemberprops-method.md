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
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177228"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="dcb9c-102">IMetaDataImport::GetMemberProps-Methode</span><span class="sxs-lookup"><span data-stu-id="dcb9c-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="dcb9c-103">Ruft Informationen ab, die in den Metadaten für eine angegebene Elementdefinition gespeichert <xref:System.Type> sind, einschließlich des Namens, der Binärsignatur und der relativen virtuellen Adresse des Elements, auf das durch das angegebene Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="dcb9c-104">Dies ist eine einfache Hilfsmethode: Wenn *mb* ein MethodDef ist, wird **GetMethodProps** aufgerufen; Wenn *mb* ein FieldDef ist, wird **GetFieldProps** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="dcb9c-105">Weitere Informationen finden Sie unter diesen anderen Methoden.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="dcb9c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcb9c-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="dcb9c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="dcb9c-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="dcb9c-108">[in] Das Token, das auf das Mitglied verweist, für das die zugehörigen Metadaten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="dcb9c-109">[out] Ein Zeiger auf das Metadatentoken, das die Klasse des Members darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="dcb9c-110">[out] Der Name des Mitglieds.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="dcb9c-111">[in] Die Größe in breiten `szMember` Zeichen des Puffers.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="dcb9c-112">[out] Die Größe des zurückgegebenen Namens in weiten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="dcb9c-113">[out] Alle Flagwerte, die auf das Element angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="dcb9c-114">[out] Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="dcb9c-115">[out] Die Größe in `ppvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="dcb9c-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="dcb9c-116">[out] Ein Zeiger auf die relative virtuelle Adresse des Elements.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="dcb9c-117">[out] Alle Methodenimplementierungsflags, die dem Member zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="dcb9c-118">[out] Ein Flag, <xref:System.ValueType>das eine markiert.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="dcb9c-119">Es ist einer `ELEMENT_TYPE_*` der Werte.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="dcb9c-120">[out] Ein konstanter Zeichenfolgenwert, der von diesem Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="dcb9c-121">[out] Die Größe in `ppValue`Zeichen von `ppValue` , oder Null, wenn keine Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="dcb9c-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb9c-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dcb9c-122">Requirements</span></span>  
 <span data-ttu-id="dcb9c-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcb9c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb9c-124">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dcb9c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dcb9c-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dcb9c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcb9c-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcb9c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb9c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcb9c-127">See also</span></span>

- [<span data-ttu-id="dcb9c-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dcb9c-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dcb9c-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dcb9c-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
