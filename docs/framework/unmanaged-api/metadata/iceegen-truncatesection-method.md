---
title: ICeeGen::TruncateSection-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7b21179faec0b6f37b8084c9ee8a0bfd327193e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443563"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="e7c79-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="e7c79-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="e7c79-103">Schneidet die im Abschnitt angegebenen Code anhand der angegebenen Länge ab.</span><span class="sxs-lookup"><span data-stu-id="e7c79-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="e7c79-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7c79-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c79-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7c79-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7c79-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7c79-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e7c79-107">[in] Im Abschnitt zum Abschneiden.</span><span class="sxs-lookup"><span data-stu-id="e7c79-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="e7c79-108">[in] Die Länge in Bytes, die im Abschnitt abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="e7c79-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7c79-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7c79-109">Remarks</span></span>  
 <span data-ttu-id="e7c79-110">Rufen Sie `TruncateSection` nur bei besonderen Anforderungen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e7c79-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c79-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7c79-111">Requirements</span></span>  
 <span data-ttu-id="e7c79-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7c79-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7c79-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7c79-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7c79-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e7c79-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7c79-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7c79-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c79-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7c79-116">See Also</span></span>  
 [<span data-ttu-id="e7c79-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7c79-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
