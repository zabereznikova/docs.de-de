---
title: ICeeGen::TruncateSection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.TruncateSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="48f9f-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="48f9f-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="48f9f-103">Schneidet die im Abschnitt angegebenen Code anhand der angegebenen Länge ab.</span><span class="sxs-lookup"><span data-stu-id="48f9f-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="48f9f-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48f9f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f9f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48f9f-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48f9f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="48f9f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="48f9f-107">[in] Im Abschnitt zum Abschneiden.</span><span class="sxs-lookup"><span data-stu-id="48f9f-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="48f9f-108">[in] Die Länge in Bytes, die im Abschnitt abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="48f9f-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48f9f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48f9f-109">Remarks</span></span>  
 <span data-ttu-id="48f9f-110">Rufen Sie `TruncateSection` nur bei besonderen Anforderungen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="48f9f-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f9f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48f9f-111">Requirements</span></span>  
 <span data-ttu-id="48f9f-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f9f-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48f9f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48f9f-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="48f9f-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48f9f-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f9f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48f9f-116">See Also</span></span>  
 [<span data-ttu-id="48f9f-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48f9f-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
