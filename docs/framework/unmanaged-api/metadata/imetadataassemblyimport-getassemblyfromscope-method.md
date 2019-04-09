---
title: IMetaDataAssemblyImport::GetAssemblyFromScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4797c952bfec4e0863e7a12b97e038c7ff8d95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191522"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="f28f2-102">IMetaDataAssemblyImport::GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="f28f2-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="f28f2-103">Ruft einen Zeiger auf der Assembly im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="f28f2-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f28f2-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f28f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f28f2-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="f28f2-106">[out] Ein Zeiger auf die abgerufenen `mdAssembly` Token, das die Assembly identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f28f2-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f28f2-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f28f2-107">Requirements</span></span>  
 <span data-ttu-id="f28f2-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f28f2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f28f2-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f28f2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f28f2-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f28f2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f28f2-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f28f2-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f28f2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f28f2-112">See also</span></span>

- [<span data-ttu-id="f28f2-113">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f28f2-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
