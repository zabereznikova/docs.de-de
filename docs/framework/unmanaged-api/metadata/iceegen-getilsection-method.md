---
title: ICeeGen::GetIlSection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4805e9421a80954c01ba1ffb6e04332c07e5d84e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="aa574-102">ICeeGen::GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="aa574-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="aa574-103">Ruft den Abschnitt der Codebasis intermediate Language auf dem angegebenen Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="aa574-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="aa574-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa574-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa574-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa574-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa574-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa574-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="aa574-107">[in] Das Handle für den Abschnitt zum Abrufen.</span><span class="sxs-lookup"><span data-stu-id="aa574-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa574-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa574-108">Requirements</span></span>  
 <span data-ttu-id="aa574-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa574-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa574-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa574-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa574-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="aa574-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa574-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa574-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa574-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa574-113">See Also</span></span>  
 [<span data-ttu-id="aa574-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa574-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
