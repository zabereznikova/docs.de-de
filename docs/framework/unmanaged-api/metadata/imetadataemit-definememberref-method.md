---
title: IMetaDataEmit::DefineMemberRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175836"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="07cc7-102">IMetaDataEmit::DefineMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="07cc7-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="07cc7-103">Definiert einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweisdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="07cc7-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07cc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07cc7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07cc7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07cc7-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="07cc7-106">[in] Token für die Klasse oder Schnittstelle des Zielmembers, wenn der Member nicht global ist; Wenn das Element global `mdModuleRef` ist, das Token für diese andere Datei.</span><span class="sxs-lookup"><span data-stu-id="07cc7-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="07cc7-107">[in] Der Name des Zielmitglieds.</span><span class="sxs-lookup"><span data-stu-id="07cc7-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="07cc7-108">[in] Die Signatur des Zielmitglieds.</span><span class="sxs-lookup"><span data-stu-id="07cc7-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="07cc7-109">[in] Die Anzahl der `pvSigBlob`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="07cc7-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="07cc7-110">[out] Das `mdMemberRef` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="07cc7-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07cc7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07cc7-111">Requirements</span></span>  
 <span data-ttu-id="07cc7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07cc7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07cc7-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07cc7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07cc7-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="07cc7-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07cc7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07cc7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cc7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07cc7-116">See also</span></span>

- [<span data-ttu-id="07cc7-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07cc7-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07cc7-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07cc7-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
