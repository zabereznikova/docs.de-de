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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 881c0b1f755e750efcc74ca61a60bbd97bc5dba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444463"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="66508-102">IMetaDataEmit::DefineMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="66508-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="66508-103">Einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs definiert, und ruft ein Token für diese Verweisdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="66508-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66508-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66508-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66508-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66508-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="66508-106">[in] Token für des Zielelements Klasse oder Schnittstelle, wenn das Element nicht global ist; Wenn das Element global ist, ist die `mdModuleRef` token für die andere Datei.</span><span class="sxs-lookup"><span data-stu-id="66508-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="66508-107">[in] Der Name des Zielelements.</span><span class="sxs-lookup"><span data-stu-id="66508-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="66508-108">[in] Die Signatur des Zielelements.</span><span class="sxs-lookup"><span data-stu-id="66508-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="66508-109">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="66508-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="66508-110">[out] Die `mdMemberRef` Token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="66508-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66508-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66508-111">Requirements</span></span>  
 <span data-ttu-id="66508-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66508-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66508-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66508-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66508-114">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="66508-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66508-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66508-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66508-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66508-116">See Also</span></span>  
 [<span data-ttu-id="66508-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66508-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="66508-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66508-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
