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
ms.openlocfilehash: 3005db62bba4089c669a00f62e3c1e62f9e1dae9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685699"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="bc51d-102">ICeeGen::TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="bc51d-102">ICeeGen::TruncateSection Method</span></span>

<span data-ttu-id="bc51d-103">Verkürzt den angegebenen Code Abschnitt um die angegebene Länge.</span><span class="sxs-lookup"><span data-stu-id="bc51d-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="bc51d-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc51d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc51d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc51d-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc51d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc51d-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="bc51d-107">in Der Abschnitt, der abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc51d-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="bc51d-108">in Die Länge in Byte, um die der Abschnitt abgeschnitten werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc51d-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc51d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc51d-109">Remarks</span></span>  

 <span data-ttu-id="bc51d-110">`TruncateSection`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="bc51d-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc51d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bc51d-111">Requirements</span></span>  

 <span data-ttu-id="bc51d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc51d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc51d-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bc51d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc51d-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc51d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc51d-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc51d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc51d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc51d-116">See also</span></span>

- [<span data-ttu-id="bc51d-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc51d-117">ICeeGen Interface</span></span>](iceegen-interface.md)
