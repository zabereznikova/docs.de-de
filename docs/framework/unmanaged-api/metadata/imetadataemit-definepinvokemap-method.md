---
title: IMetaDataEmit::DefinePinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f1d62c55df410d284fe050b805cf465718ab112
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576150"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="edfe8-102">IMetaDataEmit::DefinePinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="edfe8-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="edfe8-103">Legt die Funktionen von PInvoke-Signatur der Methode auf, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="edfe8-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfe8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edfe8-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edfe8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edfe8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="edfe8-106">[in] Das Token für die Zielmethode.</span><span class="sxs-lookup"><span data-stu-id="edfe8-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="edfe8-107">[in] Flags, die von PInvoke verwendet, um die Zuordnung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="edfe8-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="edfe8-108">[in] Der Name des Ziels export-Methode in einer nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="edfe8-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="edfe8-109">[in] Das Token für die systemeigene DLL.</span><span class="sxs-lookup"><span data-stu-id="edfe8-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edfe8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edfe8-110">Requirements</span></span>  
 <span data-ttu-id="edfe8-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edfe8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edfe8-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="edfe8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edfe8-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="edfe8-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edfe8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edfe8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfe8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edfe8-115">See also</span></span>
- [<span data-ttu-id="edfe8-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edfe8-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="edfe8-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edfe8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
