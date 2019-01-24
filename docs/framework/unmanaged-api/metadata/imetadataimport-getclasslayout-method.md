---
title: IMetaDataImport::GetClassLayout-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52136426be9e8f220d8eb5fc93659f588f007498
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625103"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="3fdf8-102">IMetaDataImport::GetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="3fdf8-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="3fdf8-103">Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fdf8-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fdf8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fdf8-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3fdf8-106">[in] Die TypeDef-Token für die Klasse mit dem Layout zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="3fdf8-107">[out] Einer der Werte 1, 2, 4, 8 oder 16 ist, werden die Paketgröße der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="3fdf8-108">[out] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3fdf8-109">[in] Die maximale Größe des `rFieldOffset`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="3fdf8-110">[out] Die Anzahl der Elemente, die in zurückgegebenen `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="3fdf8-111">[out] Die Größe in Bytes der durch dargestellten Klasse `td`.</span><span class="sxs-lookup"><span data-stu-id="3fdf8-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdf8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fdf8-112">Requirements</span></span>  
 <span data-ttu-id="3fdf8-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fdf8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fdf8-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3fdf8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fdf8-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3fdf8-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fdf8-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdf8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdf8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fdf8-117">See also</span></span>
- [<span data-ttu-id="3fdf8-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fdf8-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3fdf8-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fdf8-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
