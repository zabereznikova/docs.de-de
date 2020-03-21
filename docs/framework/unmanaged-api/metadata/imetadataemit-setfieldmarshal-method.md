---
title: IMetaDataEmit::SetFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175654"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="be252-102">IMetaDataEmit::SetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="be252-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="be252-103">Legt die PInvoke-Marshallinginformationen für den Feld-, Methodenrückgabe- oder Methodenparameter fest, auf den vom angegebenen Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="be252-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be252-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be252-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be252-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be252-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="be252-106">[in] Das Token für das Zieldatenelement.</span><span class="sxs-lookup"><span data-stu-id="be252-106">[in] The token for target data item.</span></span> <span data-ttu-id="be252-107">Dies ist `mdFieldDef` entweder `mdParamDef` ein oder ein Token.</span><span class="sxs-lookup"><span data-stu-id="be252-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="be252-108">[in] Die Signatur für nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="be252-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="be252-109">[in] Die Anzahl der `pvNativeType`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="be252-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be252-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="be252-110">Requirements</span></span>  
 <span data-ttu-id="be252-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be252-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be252-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be252-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be252-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="be252-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be252-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be252-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be252-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be252-115">See also</span></span>

- [<span data-ttu-id="be252-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be252-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="be252-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be252-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
