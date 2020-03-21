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
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175524"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="0e9d7-102">IMetaDataImport::EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="0e9d7-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="0e9d7-103">Zählt benutzerdefinierte Attributdefinitionstoken auf, die dem angegebenen Typ oder Member zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e9d7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e9d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e9d7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0e9d7-106">[in, out] Ein Zeiger auf den zurückgegebenen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="0e9d7-107">[in] Ein Token für den Bereich der Enumeration oder Null für alle benutzerdefinierten Attribute.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="0e9d7-108">[in] Ein Token für den Konstruktor des Typs der attribute, `null` die aufgezählt werden sollen, oder für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="0e9d7-109">[out] Ein Array benutzerdefinierter Attributtoken.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0e9d7-110">[in] Die maximale Größe des `rCustomAttributes`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="0e9d7-111">[out, optional] Die tatsächliche Anzahl der `rCustomAttributes`token werte, die in zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e9d7-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e9d7-112">Return Value</span></span>  
  
|<span data-ttu-id="0e9d7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e9d7-113">HRESULT</span></span>|<span data-ttu-id="0e9d7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e9d7-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0e9d7-115">`EnumCustomAttributes`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0e9d7-116">Es sind keine benutzerdefinierten Attribute zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="0e9d7-117">In diesem `pcCustomAttributes` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="0e9d7-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e9d7-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0e9d7-118">Requirements</span></span>  
 <span data-ttu-id="0e9d7-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e9d7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e9d7-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e9d7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e9d7-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0e9d7-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e9d7-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9d7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e9d7-123">See also</span></span>

- [<span data-ttu-id="0e9d7-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e9d7-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0e9d7-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e9d7-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
