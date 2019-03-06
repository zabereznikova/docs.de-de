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
ms.openlocfilehash: 69f536e6add43d664eba436e185275632dc0063a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479349"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="05d6a-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="05d6a-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="05d6a-103">Schneidet den angegebenen Codeabschnitt durch die angegebene Länge ab.</span><span class="sxs-lookup"><span data-stu-id="05d6a-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="05d6a-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05d6a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d6a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d6a-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d6a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="05d6a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="05d6a-107">[in] Der Abschnitt zum Abschneiden.</span><span class="sxs-lookup"><span data-stu-id="05d6a-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="05d6a-108">[in] Die Länge in Bytes, um Sie im Abschnitt zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="05d6a-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05d6a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05d6a-109">Remarks</span></span>  
 <span data-ttu-id="05d6a-110">Rufen Sie `TruncateSection` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="05d6a-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d6a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05d6a-111">Requirements</span></span>  
 <span data-ttu-id="05d6a-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d6a-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05d6a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05d6a-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="05d6a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05d6a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d6a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05d6a-116">See also</span></span>
- [<span data-ttu-id="05d6a-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05d6a-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
