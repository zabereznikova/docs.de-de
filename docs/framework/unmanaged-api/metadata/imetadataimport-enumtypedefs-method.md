---
title: IMetaDataImport::EnumTypeDefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177294"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="938de-102">IMetaDataImport::EnumTypeDefs-Methode</span><span class="sxs-lookup"><span data-stu-id="938de-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="938de-103">Zählt TypeDef-Token auf, die alle Typen innerhalb des aktuellen Bereichs darstellen.</span><span class="sxs-lookup"><span data-stu-id="938de-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="938de-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="938de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="938de-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="938de-106">[out] Ein Zeiger auf den neuen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="938de-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="938de-107">Dies muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="938de-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="938de-108">[in] Das Array, das zum Speichern der TypeDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="938de-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="938de-109">[in] Die maximale Größe des `rTypeDefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="938de-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="938de-110">[out] Die Anzahl der in zurückgegebenen `rTypeDefs`TypeDef-Token.</span><span class="sxs-lookup"><span data-stu-id="938de-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="938de-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="938de-111">Return Value</span></span>  
  
|<span data-ttu-id="938de-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="938de-112">HRESULT</span></span>|<span data-ttu-id="938de-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="938de-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="938de-114">`EnumTypeDefs`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="938de-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="938de-115">Es sind keine Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="938de-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="938de-116">In diesem `pcTypeDefs` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="938de-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="938de-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="938de-117">Remarks</span></span>  
 <span data-ttu-id="938de-118">Das TypeDef-Token stellt einen Typ wie eine Klasse oder eine Schnittstelle sowie jeden Typ dar, der über einen Erweiterbarkeitsmechanismus hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="938de-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="938de-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="938de-119">Requirements</span></span>  
 <span data-ttu-id="938de-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="938de-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="938de-121">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="938de-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="938de-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="938de-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="938de-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="938de-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938de-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="938de-124">See also</span></span>

- [<span data-ttu-id="938de-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="938de-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="938de-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="938de-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
