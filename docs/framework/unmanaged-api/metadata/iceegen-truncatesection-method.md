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
ms.openlocfilehash: 87a70587027f283ef5976089b3f2daf1204e68ec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426135"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="383af-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="383af-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="383af-103">Verkürzt den angegebenen Code Abschnitt um die angegebene Länge.</span><span class="sxs-lookup"><span data-stu-id="383af-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="383af-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="383af-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="383af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="383af-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="383af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="383af-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="383af-107">in Der Abschnitt, der abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="383af-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="383af-108">in Die Länge in Byte, um die der Abschnitt abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="383af-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="383af-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="383af-109">Remarks</span></span>  
 <span data-ttu-id="383af-110">Wenn Sie über besondere Abschnitts Anforderungen verfügen, die nicht von anderen Methoden behandelt werden, wenden Sie `TruncateSection` nur an.</span><span class="sxs-lookup"><span data-stu-id="383af-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="383af-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="383af-111">Requirements</span></span>  
 <span data-ttu-id="383af-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="383af-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="383af-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="383af-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="383af-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="383af-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="383af-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="383af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383af-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="383af-116">See also</span></span>

- [<span data-ttu-id="383af-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="383af-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
