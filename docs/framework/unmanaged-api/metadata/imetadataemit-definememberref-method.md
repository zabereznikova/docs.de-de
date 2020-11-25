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
ms.openlocfilehash: 597ba1884351ee6d8b7eb7e0f3f01ce3ad733304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716654"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="25a51-102">IMetaDataEmit::DefineMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="25a51-102">IMetaDataEmit::DefineMemberRef Method</span></span>

<span data-ttu-id="25a51-103">Definiert einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweis Definition ab.</span><span class="sxs-lookup"><span data-stu-id="25a51-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25a51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25a51-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25a51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25a51-105">Parameters</span></span>  

 `tkImport`  
 <span data-ttu-id="25a51-106">in Token für die Klasse oder Schnittstelle des Zielmembers, wenn der Member nicht global ist. Wenn der Member Global ist, das `mdModuleRef` Token für die andere Datei.</span><span class="sxs-lookup"><span data-stu-id="25a51-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="25a51-107">in Der Name des Zielmembers.</span><span class="sxs-lookup"><span data-stu-id="25a51-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="25a51-108">in Die Signatur des Zielmembers.</span><span class="sxs-lookup"><span data-stu-id="25a51-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="25a51-109">in Die Anzahl von Bytes in `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="25a51-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="25a51-110">vorgenommen Das `mdMemberRef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="25a51-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25a51-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="25a51-111">Requirements</span></span>  

 <span data-ttu-id="25a51-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a51-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25a51-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="25a51-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25a51-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a51-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25a51-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25a51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a51-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25a51-116">See also</span></span>

- [<span data-ttu-id="25a51-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25a51-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="25a51-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25a51-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
