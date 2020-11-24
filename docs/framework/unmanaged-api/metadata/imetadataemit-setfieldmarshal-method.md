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
ms.openlocfilehash: d479416f5f1cb4042f9b3fc112e22b67e37d3f78
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672707"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="921bd-102">IMetaDataEmit::SetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="921bd-102">IMetaDataEmit::SetFieldMarshal Method</span></span>

<span data-ttu-id="921bd-103">Legt die PInvoke-Marshallinginformationen für das Feld, die Methoden Rückgabe oder den Methoden Parameter fest, auf den vom angegebenen Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="921bd-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="921bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="921bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="921bd-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="921bd-106">in Das Token für das Ziel Datenelement.</span><span class="sxs-lookup"><span data-stu-id="921bd-106">[in] The token for target data item.</span></span> <span data-ttu-id="921bd-107">Dabei handelt es sich entweder um ein- `mdFieldDef` oder- `mdParamDef` Token.</span><span class="sxs-lookup"><span data-stu-id="921bd-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="921bd-108">in Die Signatur für den nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="921bd-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="921bd-109">in Die Anzahl von Bytes in `pvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="921bd-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="921bd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="921bd-110">Requirements</span></span>  

 <span data-ttu-id="921bd-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="921bd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="921bd-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="921bd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="921bd-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="921bd-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="921bd-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="921bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921bd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="921bd-115">See also</span></span>

- [<span data-ttu-id="921bd-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="921bd-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="921bd-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="921bd-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
