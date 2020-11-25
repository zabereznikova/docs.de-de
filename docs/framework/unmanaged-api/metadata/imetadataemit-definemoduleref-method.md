---
title: IMetaDataEmit::DefineModuleRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: 96d24705d80dabcda691edec497a4a30b6d37dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719553"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="252b6-102">IMetaDataEmit::DefineModuleRef-Methode</span><span class="sxs-lookup"><span data-stu-id="252b6-102">IMetaDataEmit::DefineModuleRef Method</span></span>

<span data-ttu-id="252b6-103">Erstellt die Metadatensignatur für ein Modul mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="252b6-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="252b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="252b6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="252b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="252b6-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="252b6-106">in Der Name der anderen Metadatendatei, in der Regel eine DLL.</span><span class="sxs-lookup"><span data-stu-id="252b6-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="252b6-107">Dies ist nur der Dateiname.</span><span class="sxs-lookup"><span data-stu-id="252b6-107">This is the file name only.</span></span> <span data-ttu-id="252b6-108">Verwenden Sie keinen vollständigen Pfadnamen.</span><span class="sxs-lookup"><span data-stu-id="252b6-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="252b6-109">vorgenommen Das zugewiesene `mdModuleRef` Token.</span><span class="sxs-lookup"><span data-stu-id="252b6-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="252b6-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="252b6-110">Requirements</span></span>  

 <span data-ttu-id="252b6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="252b6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="252b6-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="252b6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="252b6-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="252b6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="252b6-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="252b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="252b6-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="252b6-115">See also</span></span>

- [<span data-ttu-id="252b6-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="252b6-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="252b6-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="252b6-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
