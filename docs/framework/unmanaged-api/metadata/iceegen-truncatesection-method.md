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
ms.openlocfilehash: 1036d6080bf17eea288724c7980ce53dfa2121f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116320"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="364c3-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="364c3-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="364c3-103">Schneidet den angegebenen Codeabschnitt durch die angegebene Länge ab.</span><span class="sxs-lookup"><span data-stu-id="364c3-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="364c3-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="364c3-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="364c3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="364c3-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="364c3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="364c3-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="364c3-107">[in] Der Abschnitt zum Abschneiden.</span><span class="sxs-lookup"><span data-stu-id="364c3-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="364c3-108">[in] Die Länge in Bytes, um Sie im Abschnitt zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="364c3-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="364c3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="364c3-109">Remarks</span></span>  
 <span data-ttu-id="364c3-110">Rufen Sie `TruncateSection` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="364c3-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="364c3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="364c3-111">Requirements</span></span>  
 <span data-ttu-id="364c3-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="364c3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="364c3-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="364c3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="364c3-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="364c3-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="364c3-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="364c3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364c3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364c3-116">See also</span></span>

- [<span data-ttu-id="364c3-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="364c3-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
