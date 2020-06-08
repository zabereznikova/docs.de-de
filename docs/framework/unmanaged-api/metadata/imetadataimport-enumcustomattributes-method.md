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
ms.openlocfilehash: 9b0da8a06259fe99da52497da3011da94289d301
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492316"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="25145-102">IMetaDataImport::EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="25145-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="25145-103">Listet benutzerdefinierte Attribut Definitions Token auf, die dem angegebenen Typ oder Member zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="25145-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25145-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25145-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="25145-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25145-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="25145-106">[in, out] Ein Zeiger auf den zurückgegebenen Enumerator.</span><span class="sxs-lookup"><span data-stu-id="25145-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="25145-107">in Ein Token für den Bereich der-Enumeration oder 0 (null) für alle benutzerdefinierten Attribute.</span><span class="sxs-lookup"><span data-stu-id="25145-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="25145-108">in Ein Token für den Konstruktor des Typs der Attribute, die aufgelistet werden sollen, oder `null` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="25145-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="25145-109">vorgenommen Ein Array von benutzerdefinierten Attribut Token.</span><span class="sxs-lookup"><span data-stu-id="25145-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="25145-110">[in] Die maximale Größe des `rCustomAttributes`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="25145-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="25145-111">[out, optional] Die tatsächliche Anzahl der Tokenwerte, die in zurückgegeben werden `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="25145-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25145-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="25145-112">Return Value</span></span>  
  
|<span data-ttu-id="25145-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25145-113">HRESULT</span></span>|<span data-ttu-id="25145-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25145-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="25145-115">`EnumCustomAttributes`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25145-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="25145-116">Es sind keine benutzerdefinierten Attribute zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="25145-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="25145-117">In diesem Fall `pcCustomAttributes` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="25145-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25145-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="25145-118">Requirements</span></span>  
 <span data-ttu-id="25145-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25145-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25145-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="25145-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25145-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="25145-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25145-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25145-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25145-123">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="25145-123">See also</span></span>

- [<span data-ttu-id="25145-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25145-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="25145-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25145-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
