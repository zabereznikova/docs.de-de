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
ms.openlocfilehash: 387f5f01f2d2589c0b34e50b69398e1feb0e77e0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008247"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="3c42b-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="3c42b-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="3c42b-103">Verkürzt den angegebenen Code Abschnitt um die angegebene Länge.</span><span class="sxs-lookup"><span data-stu-id="3c42b-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="3c42b-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c42b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c42b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c42b-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c42b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c42b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="3c42b-107">in Der Abschnitt, der abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c42b-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="3c42b-108">in Die Länge in Byte, um die der Abschnitt abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c42b-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c42b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c42b-109">Remarks</span></span>  
 <span data-ttu-id="3c42b-110">`TruncateSection`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3c42b-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c42b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3c42b-111">Requirements</span></span>  
 <span data-ttu-id="3c42b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c42b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c42b-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3c42b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c42b-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c42b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c42b-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c42b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c42b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c42b-116">See also</span></span>

- [<span data-ttu-id="3c42b-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c42b-117">ICeeGen Interface</span></span>](iceegen-interface.md)
