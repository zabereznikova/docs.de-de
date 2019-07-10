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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 621582536c07b269dd723c9014e23c50e561957a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774614"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="16dc1-102">IMetaDataImport::EnumTypeDefs-Methode</span><span class="sxs-lookup"><span data-stu-id="16dc1-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="16dc1-103">Zählt TypeDef-Token auf, die alle Typen innerhalb des aktuellen Bereichs darstellen.</span><span class="sxs-lookup"><span data-stu-id="16dc1-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16dc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16dc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="16dc1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="16dc1-106">[out] Ein Zeiger auf den neuen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="16dc1-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="16dc1-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="16dc1-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="16dc1-108">[in] Das Array zum Speichern der TypeDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16dc1-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="16dc1-109">[in] Die maximale Größe des `rTypeDefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="16dc1-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="16dc1-110">[out] Die Anzahl der zurückgegebenen TypeDef-Token `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="16dc1-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16dc1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16dc1-111">Return Value</span></span>  
  
|<span data-ttu-id="16dc1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16dc1-112">HRESULT</span></span>|<span data-ttu-id="16dc1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16dc1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="16dc1-114">`EnumTypeDefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="16dc1-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="16dc1-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="16dc1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="16dc1-116">In diesem Fall `pcTypeDefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="16dc1-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16dc1-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16dc1-117">Remarks</span></span>  
 <span data-ttu-id="16dc1-118">Das TypeDef-Token stellt dar, einen Typ wie z. B. eine Klasse oder eine Schnittstelle als auch einen beliebigen Typ, der über keinen Erweiterbarkeitsmechanismus hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="16dc1-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16dc1-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16dc1-119">Requirements</span></span>  
 <span data-ttu-id="16dc1-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16dc1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16dc1-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="16dc1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16dc1-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="16dc1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16dc1-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16dc1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16dc1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16dc1-124">See also</span></span>

- [<span data-ttu-id="16dc1-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16dc1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="16dc1-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16dc1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
