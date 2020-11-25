---
title: IMetaDataEmit::DefineSecurityAttributeSet-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 5caf07414c9e64169f272eb11169c4d4ee399c6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719462"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="2bd4a-102">IMetaDataEmit::DefineSecurityAttributeSet-Methode</span><span class="sxs-lookup"><span data-stu-id="2bd4a-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="2bd4a-103">Erstellt einen Satz von Sicherheits Berechtigungen zum Anfügen an das Objekt, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2bd4a-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bd4a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bd4a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bd4a-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="2bd4a-106">in Das Token, an das die Sicherheitsinformationen angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2bd4a-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="2bd4a-107">in Ein Array von- `COR_SECATTR` Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2bd4a-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="2bd4a-108">in Die Anzahl der Elemente in `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="2bd4a-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="2bd4a-109">vorgenommen Wenn die Methode fehlschlägt, gibt den Index in `rSecAttrs` des Elements an, das das Problem verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="2bd4a-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bd4a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2bd4a-110">Requirements</span></span>  

 <span data-ttu-id="2bd4a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bd4a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd4a-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2bd4a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bd4a-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bd4a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bd4a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd4a-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bd4a-115">See also</span></span>

- [<span data-ttu-id="2bd4a-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bd4a-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2bd4a-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bd4a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
