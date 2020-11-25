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
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720411"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="02ff2-102">IMetaDataImport::EnumTypeDefs-Methode</span><span class="sxs-lookup"><span data-stu-id="02ff2-102">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="02ff2-103">Zählt TypeDef-Token auf, die alle Typen innerhalb des aktuellen Bereichs darstellen.</span><span class="sxs-lookup"><span data-stu-id="02ff2-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ff2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ff2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02ff2-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="02ff2-106">vorgenommen Ein Zeiger auf den neuen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="02ff2-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="02ff2-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="02ff2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="02ff2-108">in Das Array, das zum Speichern der TypeDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02ff2-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="02ff2-109">[in] Die maximale Größe des `rTypeDefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="02ff2-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="02ff2-110">vorgenommen Die Anzahl der in zurückgegebenen TypeDef-Token `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="02ff2-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02ff2-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02ff2-111">Return Value</span></span>  
  
|<span data-ttu-id="02ff2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02ff2-112">HRESULT</span></span>|<span data-ttu-id="02ff2-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02ff2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="02ff2-114">`EnumTypeDefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02ff2-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="02ff2-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="02ff2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="02ff2-116">In diesem Fall `pcTypeDefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="02ff2-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02ff2-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02ff2-117">Remarks</span></span>  

 <span data-ttu-id="02ff2-118">Das TypeDef-Token stellt einen Typ dar, z. b. eine Klasse oder eine Schnittstelle, sowie alle Typen, die über einen Erweiterbarkeits Mechanismus hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="02ff2-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ff2-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="02ff2-119">Requirements</span></span>  

 <span data-ttu-id="02ff2-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02ff2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ff2-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="02ff2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02ff2-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="02ff2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02ff2-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ff2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ff2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02ff2-124">See also</span></span>

- [<span data-ttu-id="02ff2-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02ff2-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="02ff2-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02ff2-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
