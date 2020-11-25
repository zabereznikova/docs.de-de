---
title: IMetaDataImport::EnumFields-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711584"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="161e9-102">IMetaDataImport::EnumFields-Methode</span><span class="sxs-lookup"><span data-stu-id="161e9-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="161e9-103">Zählt FieldDef-Token für den Typ auf, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="161e9-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="161e9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="161e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="161e9-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="161e9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="161e9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="161e9-107">in Das TypeDef-Token der Klasse, deren Felder aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="161e9-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="161e9-108">vorgenommen Die Liste der FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="161e9-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="161e9-109">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="161e9-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="161e9-110">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen FieldDef-Token `rFields` .</span><span class="sxs-lookup"><span data-stu-id="161e9-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="161e9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="161e9-111">Return Value</span></span>  
  
|<span data-ttu-id="161e9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="161e9-112">HRESULT</span></span>|<span data-ttu-id="161e9-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="161e9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="161e9-114">`EnumFields` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="161e9-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="161e9-115">Es sind keine Felder zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="161e9-115">There are no fields to enumerate.</span></span> <span data-ttu-id="161e9-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="161e9-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="161e9-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="161e9-117">Requirements</span></span>  

 <span data-ttu-id="161e9-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="161e9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="161e9-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="161e9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="161e9-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="161e9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="161e9-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="161e9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161e9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="161e9-122">See also</span></span>

- [<span data-ttu-id="161e9-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="161e9-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="161e9-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="161e9-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
