---
title: IMetaDataEmit::DefineTypeRefByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175745"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="23b78-102">IMetaDataEmit::DefineTypeRefByName-Methode</span><span class="sxs-lookup"><span data-stu-id="23b78-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="23b78-103">Ruft ein Metadatentoken für einen Typ ab, der im angegebenen Bereich definiert ist, der sich außerhalb des aktuellen Bereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="23b78-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23b78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23b78-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23b78-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23b78-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="23b78-106">[in] Das Token, das den Auflösungsbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="23b78-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="23b78-107">Die folgenden Tokentypen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="23b78-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="23b78-108">`mdModuleRef`, wenn der Typ in derselben Assembly definiert ist, in der der Aufrufer definiert ist.</span><span class="sxs-lookup"><span data-stu-id="23b78-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="23b78-109">`mdAssemblyRef`, wenn der Typ in einer anderen Baugruppe als der Assembly definiert ist, in der der Aufrufer definiert ist.</span><span class="sxs-lookup"><span data-stu-id="23b78-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="23b78-110">`mdTypeRef`, wenn es sich bei dem Typ um einen geschachtelten Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="23b78-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="23b78-111">`mdModule`, wenn der Typ in demselben Modul definiert ist, in dem der Aufrufer definiert ist.</span><span class="sxs-lookup"><span data-stu-id="23b78-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="23b78-112">Null, wenn der Typ global definiert ist.</span><span class="sxs-lookup"><span data-stu-id="23b78-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="23b78-113">[in] Der Name des Zieltyps in Unicode.</span><span class="sxs-lookup"><span data-stu-id="23b78-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="23b78-114">[out] Ein Zeiger auf `mdTypeRef` das Token, das dem Typ zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="23b78-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23b78-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23b78-115">Requirements</span></span>  
 <span data-ttu-id="23b78-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23b78-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23b78-117">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23b78-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23b78-118">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="23b78-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23b78-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23b78-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b78-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23b78-120">See also</span></span>

- [<span data-ttu-id="23b78-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23b78-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="23b78-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23b78-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
