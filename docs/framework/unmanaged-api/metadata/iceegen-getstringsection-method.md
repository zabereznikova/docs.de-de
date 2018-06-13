---
title: ICeeGen::GetStringSection-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a8617c9e818ec514c912a85373c916559d89df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443036"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="8ca7c-102">ICeeGen::GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="8ca7c-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="8ca7c-103">Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der dem angegebenen Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="8ca7c-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="8ca7c-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ca7c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ca7c-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ca7c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ca7c-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8ca7c-107">[in, out] Das Handle für den Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="8ca7c-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca7c-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ca7c-108">Requirements</span></span>  
 <span data-ttu-id="8ca7c-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ca7c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ca7c-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ca7c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ca7c-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8ca7c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ca7c-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca7c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca7c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ca7c-113">See Also</span></span>  
 [<span data-ttu-id="8ca7c-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ca7c-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
