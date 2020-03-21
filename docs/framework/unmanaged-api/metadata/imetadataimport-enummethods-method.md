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
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177312"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="bda1e-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="bda1e-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="bda1e-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="bda1e-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda1e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bda1e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bda1e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bda1e-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="bda1e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bda1e-107">Dies muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="bda1e-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="bda1e-108">[in] Ein TypeDef-Token, das den Typ mit den aufzuzählenden Methoden darstellt.</span><span class="sxs-lookup"><span data-stu-id="bda1e-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="bda1e-109">[out] Das Array, das die MethodDef-Token speichert.</span><span class="sxs-lookup"><span data-stu-id="bda1e-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bda1e-110">[in] Die maximale Größe des `rMethods` MethodDef-Arrays.</span><span class="sxs-lookup"><span data-stu-id="bda1e-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bda1e-111">[out] Die Anzahl der methodDef-Token, die in `rMethods`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bda1e-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bda1e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bda1e-112">Return Value</span></span>  
  
|<span data-ttu-id="bda1e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bda1e-113">HRESULT</span></span>|<span data-ttu-id="bda1e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda1e-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bda1e-115">`EnumMethods`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bda1e-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bda1e-116">Es sind keine MethodDef-Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bda1e-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="bda1e-117">In diesem `pcTokens` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="bda1e-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bda1e-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bda1e-118">Requirements</span></span>  
 <span data-ttu-id="bda1e-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda1e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda1e-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bda1e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bda1e-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bda1e-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bda1e-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda1e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda1e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bda1e-123">See also</span></span>

- [<span data-ttu-id="bda1e-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda1e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bda1e-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda1e-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
