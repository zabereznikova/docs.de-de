---
title: IMetaDataEmit::DefineUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: ed3c20fe8272ca3205079d26df0b7bde12e58307
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732696"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="c0078-102">IMetaDataEmit::DefineUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="c0078-102">IMetaDataEmit::DefineUserString Method</span></span>

<span data-ttu-id="c0078-103">Ruft ein Metadatentoken für die angegebene Literalzeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="c0078-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0078-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0078-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0078-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0078-105">Parameters</span></span>  

 `szString`  
 <span data-ttu-id="c0078-106">in Die zu Speicher-Benutzer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c0078-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="c0078-107">in Die Anzahl der breit Zeichen in `szString` .</span><span class="sxs-lookup"><span data-stu-id="c0078-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="c0078-108">vorgenommen Das zugewiesene Zeichen folgen Token.</span><span class="sxs-lookup"><span data-stu-id="c0078-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0078-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c0078-109">Requirements</span></span>  

 <span data-ttu-id="c0078-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0078-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0078-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c0078-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0078-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0078-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0078-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0078-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0078-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0078-114">See also</span></span>

- [<span data-ttu-id="c0078-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0078-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c0078-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0078-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
