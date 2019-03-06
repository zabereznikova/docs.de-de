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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18cf59553468e2408f3898d8233bd05d453db17b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471965"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="671de-102">IMetaDataImport::EnumFields-Methode</span><span class="sxs-lookup"><span data-stu-id="671de-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="671de-103">Zählt FieldDef-Token für den Typ auf, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="671de-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="671de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="671de-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="671de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="671de-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="671de-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="671de-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="671de-107">[in] Die TypeDef-Token von der Klasse, deren Felder aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="671de-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="671de-108">[out] Die Liste der FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="671de-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="671de-109">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="671de-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="671de-110">[out] Die tatsächliche Anzahl der zurückgegebenen FieldDef-Token `rFields`.</span><span class="sxs-lookup"><span data-stu-id="671de-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="671de-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="671de-111">Return Value</span></span>  
  
|<span data-ttu-id="671de-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="671de-112">HRESULT</span></span>|<span data-ttu-id="671de-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="671de-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="671de-114">`EnumFields` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="671de-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="671de-115">Es gibt keine Felder aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="671de-115">There are no fields to enumerate.</span></span> <span data-ttu-id="671de-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="671de-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="671de-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="671de-117">Requirements</span></span>  
 <span data-ttu-id="671de-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="671de-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="671de-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="671de-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="671de-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="671de-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="671de-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="671de-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671de-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="671de-122">See also</span></span>
- [<span data-ttu-id="671de-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="671de-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="671de-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="671de-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
