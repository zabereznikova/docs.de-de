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
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177735"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="d6482-102">IMetaDataEmit::DefineModuleRef-Methode</span><span class="sxs-lookup"><span data-stu-id="d6482-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="d6482-103">Erstellt die Metadatensignatur für ein Modul mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="d6482-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6482-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6482-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6482-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6482-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d6482-106">[in] Der Name der anderen Metadatendatei, in der Regel eine DLL.</span><span class="sxs-lookup"><span data-stu-id="d6482-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="d6482-107">Dies ist nur der Dateiname.</span><span class="sxs-lookup"><span data-stu-id="d6482-107">This is the file name only.</span></span> <span data-ttu-id="d6482-108">Verwenden Sie keinen vollständigen Pfadnamen.</span><span class="sxs-lookup"><span data-stu-id="d6482-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="d6482-109">[out] Das `mdModuleRef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="d6482-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6482-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d6482-110">Requirements</span></span>  
 <span data-ttu-id="d6482-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6482-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6482-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6482-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6482-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d6482-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6482-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6482-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6482-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6482-115">See also</span></span>

- [<span data-ttu-id="d6482-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6482-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d6482-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6482-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
