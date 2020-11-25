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
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711259"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="dca82-102">IMetaDataImport::GetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="dca82-102">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="dca82-103">Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dca82-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dca82-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dca82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dca82-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="dca82-106">in Das TypeDef-Token für die Klasse mit dem Layout, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="dca82-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="dca82-107">vorgenommen Einer der Werte 1, 2, 4, 8 oder 16, der die Paketgröße der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="dca82-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="dca82-108">vorgenommen Ein Array von [COR_FIELD_OFFSET](cor-field-offset-structure.md) Werten.</span><span class="sxs-lookup"><span data-stu-id="dca82-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dca82-109">[in] Die maximale Größe des `rFieldOffset`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="dca82-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="dca82-110">vorgenommen Die Anzahl der Elemente, die in zurückgegeben werden `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="dca82-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="dca82-111">vorgenommen Die Größe der durch dargestellten Klasse in Bytes `td` .</span><span class="sxs-lookup"><span data-stu-id="dca82-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca82-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dca82-112">Requirements</span></span>  

 <span data-ttu-id="dca82-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca82-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca82-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dca82-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dca82-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dca82-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dca82-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca82-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dca82-117">See also</span></span>

- [<span data-ttu-id="dca82-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dca82-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="dca82-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dca82-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
