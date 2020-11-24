---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690521"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="f3f5e-102">IMetaDataImport::EnumPermissionSets-Methode</span><span class="sxs-lookup"><span data-stu-id="f3f5e-102">IMetaDataImport::EnumPermissionSets Method</span></span>

<span data-ttu-id="f3f5e-103">Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3f5e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3f5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3f5e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="f3f5e-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f3f5e-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="f3f5e-108">in Ein Metadatentoken, das den Suchbereich einschränkt, oder NULL, um den größtmöglichen Bereich zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="f3f5e-109">in Flags, die die <xref:System.Security.Permissions.SecurityAction> Werte darstellen, die in eingeschlossen werden sollen `rPermission` , oder NULL, um alle Aktionen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="f3f5e-110">vorgenommen Das Array, das zum Speichern der Berechtigungs Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f3f5e-111">[in] Die maximale Größe des `rPermission`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f3f5e-112">vorgenommen Die Anzahl der in zurückgegebenen Berechtigungs Token `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="f3f5e-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3f5e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3f5e-113">Return Value</span></span>  
  
|<span data-ttu-id="f3f5e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3f5e-114">HRESULT</span></span>|<span data-ttu-id="f3f5e-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f3f5e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f3f5e-116">`EnumPermissionSets` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f3f5e-117">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f3f5e-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="f3f5e-118">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f3f5e-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f5e-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f3f5e-119">Requirements</span></span>  

 <span data-ttu-id="f3f5e-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f5e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f5e-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3f5e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3f5e-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f3f5e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3f5e-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f5e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f5e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3f5e-124">See also</span></span>

- [<span data-ttu-id="f3f5e-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3f5e-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f3f5e-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3f5e-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
