---
title: IMetaDataEmit::SetModuleProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86cb99023c0abfc70d292427b14986dbcea1d333
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586162"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="e56bd-102">IMetaDataEmit::SetModuleProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e56bd-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="e56bd-103">Aktualisiert die Verweise auf ein Modul definiert, die von einem vorherigen Aufruf von [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="e56bd-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e56bd-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e56bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e56bd-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e56bd-106">[in] Der Modulname im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="e56bd-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="e56bd-107">Dies ist nur den Dateinamen und nicht den vollständigen Pfadnamen.</span><span class="sxs-lookup"><span data-stu-id="e56bd-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e56bd-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e56bd-108">Requirements</span></span>  
 <span data-ttu-id="e56bd-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e56bd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e56bd-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e56bd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e56bd-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e56bd-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e56bd-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e56bd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56bd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e56bd-113">See also</span></span>
- [<span data-ttu-id="e56bd-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e56bd-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e56bd-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e56bd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
