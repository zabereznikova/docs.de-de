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
ms.openlocfilehash: ce8be38f6e146b2a8669ea5c694353615f6f2d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445902"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="234da-102">IMetaDataEmit::SetModuleProps-Methode</span><span class="sxs-lookup"><span data-stu-id="234da-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="234da-103">Aktualisiert die Verweise auf ein Modul, das durch einen vorherigen Aufruf definierten [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="234da-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="234da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="234da-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="234da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="234da-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="234da-106">[in] Der Modulname im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="234da-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="234da-107">Dies ist nur den Dateinamen und nicht den vollständigen Pfadnamen.</span><span class="sxs-lookup"><span data-stu-id="234da-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="234da-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="234da-108">Requirements</span></span>  
 <span data-ttu-id="234da-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="234da-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="234da-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="234da-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="234da-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="234da-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="234da-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="234da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234da-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="234da-113">See Also</span></span>  
 [<span data-ttu-id="234da-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="234da-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="234da-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="234da-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
