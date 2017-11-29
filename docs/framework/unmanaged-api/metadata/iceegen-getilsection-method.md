---
title: ICeeGen::GetIlSection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetIlSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b87936fb099d6e58281162d0a9a75291b0ac0767
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="6ea25-102">ICeeGen::GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="6ea25-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="6ea25-103">Ruft den Abschnitt der Codebasis intermediate Language auf dem angegebenen Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="6ea25-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="6ea25-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ea25-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea25-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ea25-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ea25-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ea25-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="6ea25-107">[in] Das Handle für den Abschnitt zum Abrufen.</span><span class="sxs-lookup"><span data-stu-id="6ea25-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea25-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ea25-108">Requirements</span></span>  
 <span data-ttu-id="6ea25-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea25-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea25-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ea25-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ea25-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6ea25-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ea25-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea25-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea25-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ea25-113">See Also</span></span>  
 [<span data-ttu-id="6ea25-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ea25-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
