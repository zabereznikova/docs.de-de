---
title: ICeeGen::EmitString-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: b9c907868df31da8d995c6a6b86db258d395335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715445"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="42a15-102">ICeeGen::EmitString-Methode</span><span class="sxs-lookup"><span data-stu-id="42a15-102">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="42a15-103">Gibt die angegebene Zeichenfolge in der Codebasis aus.</span><span class="sxs-lookup"><span data-stu-id="42a15-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="42a15-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42a15-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a15-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="42a15-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a15-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="42a15-106">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="42a15-107">in Die auszugebende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="42a15-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="42a15-108">vorgenommen Die relative virtuelle Adresse der ausgegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="42a15-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a15-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42a15-109">Requirements</span></span>  

 <span data-ttu-id="42a15-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a15-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a15-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="42a15-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42a15-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="42a15-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42a15-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42a15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a15-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42a15-114">See also</span></span>

- [<span data-ttu-id="42a15-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42a15-115">ICeeGen Interface</span></span>](iceegen-interface.md)
