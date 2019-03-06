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
ms.openlocfilehash: 0fc82ad87721c31337002dcfc5bbfdb9300afb31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479739"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="1b97d-102">IMetaDataAssemblyImport::GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="1b97d-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="1b97d-103">Ruft einen Zeiger auf der Assembly im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="1b97d-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b97d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b97d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b97d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b97d-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="1b97d-106">[out] Ein Zeiger auf die abgerufenen `mdAssembly` Token, das die Assembly identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1b97d-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b97d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b97d-107">Requirements</span></span>  
 <span data-ttu-id="1b97d-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b97d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b97d-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1b97d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b97d-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1b97d-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b97d-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b97d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b97d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b97d-112">See also</span></span>
- [<span data-ttu-id="1b97d-113">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b97d-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
