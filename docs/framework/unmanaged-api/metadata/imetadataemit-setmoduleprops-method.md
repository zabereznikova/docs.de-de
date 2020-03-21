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
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175615"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="19152-102">IMetaDataEmit::SetModuleProps-Methode</span><span class="sxs-lookup"><span data-stu-id="19152-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="19152-103">Aktualisiert Verweise auf ein Modul, das durch einen vorherigen Aufruf von [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="19152-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19152-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19152-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19152-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19152-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="19152-106">[in] Der Modulname in Unicode.</span><span class="sxs-lookup"><span data-stu-id="19152-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="19152-107">Dies ist nur der Dateiname und nicht der vollständige Pfadname.</span><span class="sxs-lookup"><span data-stu-id="19152-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19152-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19152-108">Requirements</span></span>  
 <span data-ttu-id="19152-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19152-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19152-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19152-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19152-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="19152-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19152-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19152-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19152-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19152-113">See also</span></span>

- [<span data-ttu-id="19152-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19152-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="19152-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19152-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
