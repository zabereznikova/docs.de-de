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
ms.openlocfilehash: 2d32dc8ae59fc1a4a189d849437cc95ea3b94a4d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449542"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="62ce5-102">IMetaDataImport::EnumFields-Methode</span><span class="sxs-lookup"><span data-stu-id="62ce5-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="62ce5-103">Zählt FieldDef-Token für den Typ auf, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="62ce5-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62ce5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62ce5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62ce5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62ce5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="62ce5-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="62ce5-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="62ce5-107">in Das TypeDef-Token der Klasse, deren Felder aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62ce5-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="62ce5-108">vorgenommen Die Liste der FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="62ce5-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="62ce5-109">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="62ce5-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="62ce5-110">vorgenommen Die tatsächliche Anzahl der in `rFields`zurückgegebenen FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="62ce5-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62ce5-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62ce5-111">Return Value</span></span>  
  
|<span data-ttu-id="62ce5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62ce5-112">HRESULT</span></span>|<span data-ttu-id="62ce5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62ce5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="62ce5-114">`EnumFields` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62ce5-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="62ce5-115">Es sind keine Felder zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62ce5-115">There are no fields to enumerate.</span></span> <span data-ttu-id="62ce5-116">In diesem Fall `pcTokens` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="62ce5-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62ce5-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="62ce5-117">Requirements</span></span>  
 <span data-ttu-id="62ce5-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ce5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ce5-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62ce5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62ce5-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="62ce5-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62ce5-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ce5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ce5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62ce5-122">See also</span></span>

- [<span data-ttu-id="62ce5-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62ce5-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="62ce5-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62ce5-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
