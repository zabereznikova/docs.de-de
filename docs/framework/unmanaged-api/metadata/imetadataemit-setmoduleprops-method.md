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
ms.openlocfilehash: 1757662d2004dce3156182c35b37237ff91bae7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730341"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="68b2a-102">IMetaDataEmit::SetModuleProps-Methode</span><span class="sxs-lookup"><span data-stu-id="68b2a-102">IMetaDataEmit::SetModuleProps Method</span></span>

<span data-ttu-id="68b2a-103">Aktualisiert Verweise auf ein Modul, das durch einen vorherigen [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="68b2a-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68b2a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68b2a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68b2a-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="68b2a-106">in Der Modulname in Unicode.</span><span class="sxs-lookup"><span data-stu-id="68b2a-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="68b2a-107">Dies ist nur der Dateiname und nicht der vollständige Pfadname.</span><span class="sxs-lookup"><span data-stu-id="68b2a-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b2a-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68b2a-108">Requirements</span></span>  

 <span data-ttu-id="68b2a-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68b2a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b2a-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="68b2a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68b2a-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="68b2a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68b2a-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68b2a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b2a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68b2a-113">See also</span></span>

- [<span data-ttu-id="68b2a-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68b2a-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="68b2a-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68b2a-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
