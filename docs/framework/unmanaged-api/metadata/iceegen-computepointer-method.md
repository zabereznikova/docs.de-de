---
title: ICeeGen::ComputePointer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 41a3b9c77fc766b2fa39b406dedbb3203cc97ad9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715471"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="51ebb-102">ICeeGen::ComputePointer-Methode</span><span class="sxs-lookup"><span data-stu-id="51ebb-102">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="51ebb-103">Bestimmt den Puffer für den angegebenen Code Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="51ebb-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="51ebb-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51ebb-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ebb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51ebb-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ebb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51ebb-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="51ebb-107">in Der Code Abschnitt, für den ein Puffer zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="51ebb-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="51ebb-108">in Die relative virtuelle Adresse der Methode, für die ein Zeiger erhalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="51ebb-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="51ebb-109">vorgenommen Ein Zeiger auf den zurückgegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="51ebb-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ebb-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51ebb-110">Requirements</span></span>  

 <span data-ttu-id="51ebb-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ebb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ebb-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="51ebb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51ebb-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="51ebb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51ebb-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ebb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ebb-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51ebb-115">See also</span></span>

- [<span data-ttu-id="51ebb-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51ebb-116">ICeeGen Interface</span></span>](iceegen-interface.md)
