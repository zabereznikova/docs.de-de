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
ms.openlocfilehash: 0357444aa8fa38bce5a7175cf6aacfe1a2b2b16e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503639"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="fd584-102">IMetaDataImport::GetMemberProps-Methode</span><span class="sxs-lookup"><span data-stu-id="fd584-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="fd584-103">Ruft Informationen ab, die in den Metadaten für eine angegebene Element Definition gespeichert sind, einschließlich des Namens, der binären Signatur und der relativen virtuellen Adresse des Members, auf den <xref:System.Type> das angegebene Metadatentoken verweist.</span><span class="sxs-lookup"><span data-stu-id="fd584-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="fd584-104">Dies ist eine einfache Hilfsmethode: Wenn *MB* ein MethodDef-Wert ist, wird **GetMethod-** Eigenschaften aufgerufen. Wenn *MB* ein FieldDef-Wert ist, wird **GetField-** Eigenschaften aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fd584-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="fd584-105">Weitere Informationen finden Sie in diesen anderen Methoden.</span><span class="sxs-lookup"><span data-stu-id="fd584-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="fd584-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd584-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fd584-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd584-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="fd584-108">in Das Token, das auf den Member verweist, für den die zugeordneten Metadaten zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="fd584-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fd584-109">vorgenommen Ein Zeiger auf das Metadatentoken, das die Klasse des Members darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd584-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="fd584-110">vorgenommen Der Name des Members.</span><span class="sxs-lookup"><span data-stu-id="fd584-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="fd584-111">in Die Größe des Puffers in breit Zeichen `szMember` .</span><span class="sxs-lookup"><span data-stu-id="fd584-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="fd584-112">vorgenommen Die Größe des zurückgegebenen Namens in breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fd584-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="fd584-113">vorgenommen Alle Flagwerte, die auf den Member angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd584-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="fd584-114">vorgenommen Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="fd584-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="fd584-115">vorgenommen Die Größe von in Bytes `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="fd584-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="fd584-116">vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Members.</span><span class="sxs-lookup"><span data-stu-id="fd584-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="fd584-117">vorgenommen Alle Methodenimplementierungsflags, die dem Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fd584-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fd584-118">vorgenommen Ein Flag, das eine markiert <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="fd584-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="fd584-119">Dabei handelt es sich um einen der- `ELEMENT_TYPE_*` Werte.</span><span class="sxs-lookup"><span data-stu-id="fd584-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="fd584-120">vorgenommen Ein konstanter Zeichen folgen Wert, der von diesem Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fd584-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="fd584-121">vorgenommen Die Größe in Zeichen von `ppValue` oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="fd584-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd584-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fd584-122">Requirements</span></span>  
 <span data-ttu-id="fd584-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd584-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd584-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd584-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd584-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd584-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd584-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd584-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd584-127">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fd584-127">See also</span></span>

- [<span data-ttu-id="fd584-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd584-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fd584-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd584-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
