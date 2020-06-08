---
title: IMetaDataImport::EnumMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 91ae326a89e463d26b39c1659d872130042557bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492015"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="180ab-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="180ab-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="180ab-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="180ab-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="180ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="180ab-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="180ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="180ab-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="180ab-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="180ab-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="180ab-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="180ab-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="180ab-108">in Ein TypeDef-Token, das den Typ mit den aufzuzählenden Methoden darstellt.</span><span class="sxs-lookup"><span data-stu-id="180ab-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="180ab-109">vorgenommen Das Array zum Speichern der MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="180ab-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="180ab-110">in Die maximale Größe des MethodDef- `rMethods` Arrays.</span><span class="sxs-lookup"><span data-stu-id="180ab-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="180ab-111">vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="180ab-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="180ab-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="180ab-112">Return Value</span></span>  
  
|<span data-ttu-id="180ab-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="180ab-113">HRESULT</span></span>|<span data-ttu-id="180ab-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="180ab-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="180ab-115">`EnumMethods`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="180ab-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="180ab-116">Es sind keine MethodDef-Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="180ab-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="180ab-117">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="180ab-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="180ab-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="180ab-118">Requirements</span></span>  
 <span data-ttu-id="180ab-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="180ab-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="180ab-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="180ab-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="180ab-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="180ab-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="180ab-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="180ab-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180ab-123">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="180ab-123">See also</span></span>

- [<span data-ttu-id="180ab-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="180ab-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="180ab-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="180ab-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
