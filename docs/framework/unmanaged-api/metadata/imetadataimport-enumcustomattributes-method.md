---
title: IMetaDataImport::EnumCustomAttributes-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b549c6eacad63b165d26c203817f1a2adac57bca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448637"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="d0135-102">IMetaDataImport::EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="d0135-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="d0135-103">Zählt benutzerdefinierte Attributdefinition-Token, die den angegebenen Typ oder Member zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d0135-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0135-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0135-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0135-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0135-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d0135-106">[in, out] Ein Zeiger auf den zurückgegebenen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d0135-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="d0135-107">[in] Ein Token für den Bereich der Enumeration oder 0 (null) für alle benutzerdefinierten Attribute.</span><span class="sxs-lookup"><span data-stu-id="d0135-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="d0135-108">[in] Ein Token für den Konstruktor des Typs der Attribute aufgelistet werden sollen, oder `null` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="d0135-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="d0135-109">[out] Ein Array von benutzerdefinierten Attributtoken.</span><span class="sxs-lookup"><span data-stu-id="d0135-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d0135-110">[in] Die maximale Größe des `rCustomAttributes`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d0135-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="d0135-111">[out, optional] Die tatsächliche Anzahl von Tokenwerten im zurückgegebenen `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="d0135-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0135-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0135-112">Return Value</span></span>  
  
|<span data-ttu-id="d0135-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0135-113">HRESULT</span></span>|<span data-ttu-id="d0135-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0135-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d0135-115">`EnumCustomAttributes` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0135-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d0135-116">Es sind keine benutzerdefinierten Attribute aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="d0135-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="d0135-117">In diesem Fall `pcCustomAttributes` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d0135-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0135-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0135-118">Requirements</span></span>  
 <span data-ttu-id="d0135-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0135-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0135-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0135-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0135-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d0135-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0135-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0135-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0135-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0135-123">See Also</span></span>  
 [<span data-ttu-id="d0135-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0135-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d0135-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0135-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
