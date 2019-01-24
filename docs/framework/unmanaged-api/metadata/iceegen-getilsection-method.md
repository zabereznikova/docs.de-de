---
title: ICeeGen::GetIlSection-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e75f46d73e068c6bdaac6ae01740ecf589c97d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635909"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="06df1-102">ICeeGen::GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="06df1-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="06df1-103">Ruft ab, der Teil der Zwischensprache Codebasis auf das angegebene Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="06df1-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="06df1-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06df1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06df1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="06df1-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06df1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="06df1-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="06df1-107">[in] Das Handle für den Abschnitt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="06df1-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06df1-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06df1-108">Requirements</span></span>  
 <span data-ttu-id="06df1-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06df1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06df1-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="06df1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06df1-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="06df1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06df1-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06df1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06df1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06df1-113">See also</span></span>
- [<span data-ttu-id="06df1-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06df1-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
