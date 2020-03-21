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
ms.openlocfilehash: be2845d1d660d86447cfbb6f2845a8e68b727e66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175511"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="be01c-102">IMetaDataImport::EnumFields-Methode</span><span class="sxs-lookup"><span data-stu-id="be01c-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="be01c-103">Zählt FieldDef-Token für den Typ auf, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="be01c-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be01c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be01c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be01c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be01c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="be01c-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="be01c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="be01c-107">[in] Das TypeDef-Token der Klasse, deren Felder aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be01c-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="be01c-108">[out] Die Liste der FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="be01c-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="be01c-109">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="be01c-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="be01c-110">[out] Die tatsächliche Anzahl der FieldDef-Token, die in `rFields`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be01c-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be01c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="be01c-111">Return Value</span></span>  
  
|<span data-ttu-id="be01c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be01c-112">HRESULT</span></span>|<span data-ttu-id="be01c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be01c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="be01c-114">`EnumFields`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be01c-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="be01c-115">Es sind keine Felder zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="be01c-115">There are no fields to enumerate.</span></span> <span data-ttu-id="be01c-116">In diesem `pcTokens` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="be01c-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be01c-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="be01c-117">Requirements</span></span>  
 <span data-ttu-id="be01c-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be01c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be01c-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be01c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be01c-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="be01c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be01c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be01c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be01c-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be01c-122">See also</span></span>

- [<span data-ttu-id="be01c-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be01c-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="be01c-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be01c-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
