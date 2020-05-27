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
ms.openlocfilehash: 576f4561ed782f091840ac378831110a1bfef9c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004691"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="63577-102">IMetaDataEmit::DefineMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="63577-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="63577-103">Definiert einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweis Definition ab.</span><span class="sxs-lookup"><span data-stu-id="63577-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63577-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63577-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63577-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63577-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="63577-106">in Token für die Klasse oder Schnittstelle des Zielmembers, wenn der Member nicht global ist. Wenn der Member Global ist, das `mdModuleRef` Token für die andere Datei.</span><span class="sxs-lookup"><span data-stu-id="63577-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="63577-107">in Der Name des Zielmembers.</span><span class="sxs-lookup"><span data-stu-id="63577-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="63577-108">in Die Signatur des Zielmembers.</span><span class="sxs-lookup"><span data-stu-id="63577-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="63577-109">in Die Anzahl von Bytes in `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="63577-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="63577-110">vorgenommen Das `mdMemberRef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="63577-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63577-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="63577-111">Requirements</span></span>  
 <span data-ttu-id="63577-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63577-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63577-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="63577-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63577-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="63577-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63577-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63577-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63577-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63577-116">See also</span></span>

- [<span data-ttu-id="63577-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63577-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="63577-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63577-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
