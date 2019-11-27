---
title: IMetaDataImport::EnumMethodImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: 193e8788d5a1b28f43f2fb0d4d935a18542dd923
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427493"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="ce160-102">IMetaDataImport::EnumMethodImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="ce160-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="ce160-103">Zählt MethodBody- und MethodDeclaration-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="ce160-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce160-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce160-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce160-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce160-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ce160-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="ce160-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ce160-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="ce160-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="ce160-108">in Ein TypeDef-Token für den Typ, dessen Methoden Implementierungen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce160-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="ce160-109">vorgenommen Das Array zum Speichern der MethodBody-Token.</span><span class="sxs-lookup"><span data-stu-id="ce160-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="ce160-110">vorgenommen Das Array zum Speichern der MethodDeclaration-Token.</span><span class="sxs-lookup"><span data-stu-id="ce160-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ce160-111">in Die maximale Größe des `rMethodBody` und `rMethodDecl` Arrays.</span><span class="sxs-lookup"><span data-stu-id="ce160-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ce160-112">in Die tatsächliche Anzahl von Methoden, die in `rMethodBody` und `rMethodDecl`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ce160-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce160-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce160-113">Return Value</span></span>  
  
|<span data-ttu-id="ce160-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce160-114">HRESULT</span></span>|<span data-ttu-id="ce160-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce160-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ce160-116">`EnumMethodImpls` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce160-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ce160-117">Es sind keine Methoden Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ce160-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="ce160-118">In diesem Fall `pcTokens` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="ce160-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce160-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ce160-119">Requirements</span></span>  
 <span data-ttu-id="ce160-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce160-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce160-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce160-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce160-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce160-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce160-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce160-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce160-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce160-124">See also</span></span>

- [<span data-ttu-id="ce160-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce160-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ce160-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce160-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
