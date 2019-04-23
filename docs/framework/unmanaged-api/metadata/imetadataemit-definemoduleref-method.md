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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128816"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="4b6d1-102">IMetaDataEmit::DefineModuleRef-Methode</span><span class="sxs-lookup"><span data-stu-id="4b6d1-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="4b6d1-103">Erstellt die Signatur der Metadaten für ein Modul mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="4b6d1-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b6d1-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b6d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b6d1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="4b6d1-106">[in] Der Name der anderen Metadaten-Datei, in der Regel eine DLL-Datei.</span><span class="sxs-lookup"><span data-stu-id="4b6d1-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="4b6d1-107">Dies ist nur den Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="4b6d1-107">This is the file name only.</span></span> <span data-ttu-id="4b6d1-108">Verwenden Sie keinen vollständigen Pfadnamen.</span><span class="sxs-lookup"><span data-stu-id="4b6d1-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="4b6d1-109">[out] Die zugewiesene `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="4b6d1-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b6d1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b6d1-110">Requirements</span></span>  
 <span data-ttu-id="4b6d1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b6d1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b6d1-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b6d1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b6d1-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4b6d1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b6d1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b6d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6d1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b6d1-115">See also</span></span>

- [<span data-ttu-id="4b6d1-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b6d1-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4b6d1-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b6d1-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
