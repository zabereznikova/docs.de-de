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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63ddd3b5cc79cedba6d6acc6a9b6b70c00d917fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476229"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="673d5-102">ICeeGen::EmitString-Methode</span><span class="sxs-lookup"><span data-stu-id="673d5-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="673d5-103">Gibt die angegebene Zeichenfolge in die CodeBase.</span><span class="sxs-lookup"><span data-stu-id="673d5-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="673d5-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="673d5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="673d5-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="673d5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="673d5-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="673d5-107">[in] Die Zeichenfolge ausgeben.</span><span class="sxs-lookup"><span data-stu-id="673d5-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="673d5-108">[out] Die relative virtuelle Adresse der Zeichenfolge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="673d5-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673d5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="673d5-109">Requirements</span></span>  
 <span data-ttu-id="673d5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="673d5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673d5-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="673d5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="673d5-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="673d5-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="673d5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="673d5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673d5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="673d5-114">See also</span></span>
- [<span data-ttu-id="673d5-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="673d5-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
