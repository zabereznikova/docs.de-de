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
ms.openlocfilehash: e02d7dd4b287d027b633ae9bf2e98e036062bdd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175407"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="dc740-102">IMetaDataImport::GetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="dc740-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="dc740-103">Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dc740-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc740-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc740-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc740-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc740-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="dc740-106">[in] Das TypeDef-Token für die Klasse, für die das Layout zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc740-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="dc740-107">[out] Einer der Werte 1, 2, 4, 8 oder 16, der die Packungsgröße der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc740-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="dc740-108">[out] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Werten.</span><span class="sxs-lookup"><span data-stu-id="dc740-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dc740-109">[in] Die maximale Größe des `rFieldOffset`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="dc740-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="dc740-110">[out] Die Anzahl der `rFieldOffset`elemente, die in zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dc740-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="dc740-111">[out] Die Größe in Bytes der `td`Klasse, die durch dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc740-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc740-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dc740-112">Requirements</span></span>  
 <span data-ttu-id="dc740-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc740-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc740-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc740-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc740-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc740-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc740-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc740-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc740-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc740-117">See also</span></span>

- [<span data-ttu-id="dc740-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc740-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dc740-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc740-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
