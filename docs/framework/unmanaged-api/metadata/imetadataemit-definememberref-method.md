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
ms.openlocfilehash: d5d386b1d3f95e703cc5d9ad1353ea6b84b5b455
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176045"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="f8575-102">IMetaDataEmit::DefineMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="f8575-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="f8575-103">Definiert einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweisdefinition.</span><span class="sxs-lookup"><span data-stu-id="f8575-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8575-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8575-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8575-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8575-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="f8575-106">[in] Token für des Zielmembers Klasse oder Schnittstelle, wenn das Element nicht global ist; Wenn das Element global, ist die `mdModuleRef` token für die andere Datei.</span><span class="sxs-lookup"><span data-stu-id="f8575-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="f8575-107">[in] Der Name des Zielmembers.</span><span class="sxs-lookup"><span data-stu-id="f8575-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f8575-108">[in] Die Signatur des Target-Elements.</span><span class="sxs-lookup"><span data-stu-id="f8575-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f8575-109">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f8575-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="f8575-110">[out] Die `mdMemberRef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="f8575-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8575-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8575-111">Requirements</span></span>  
 <span data-ttu-id="f8575-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8575-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8575-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8575-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8575-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f8575-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8575-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8575-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8575-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8575-116">See also</span></span>

- [<span data-ttu-id="f8575-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8575-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f8575-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8575-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
