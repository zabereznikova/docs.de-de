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
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045037"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="89a81-102">ICeeGen::EmitString-Methode</span><span class="sxs-lookup"><span data-stu-id="89a81-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="89a81-103">Gibt die angegebene Zeichenfolge in die CodeBase.</span><span class="sxs-lookup"><span data-stu-id="89a81-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="89a81-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89a81-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a81-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="89a81-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a81-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="89a81-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="89a81-107">[in] Die Zeichenfolge ausgeben.</span><span class="sxs-lookup"><span data-stu-id="89a81-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="89a81-108">[out] Die relative virtuelle Adresse der Zeichenfolge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="89a81-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a81-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89a81-109">Requirements</span></span>  
 <span data-ttu-id="89a81-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a81-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89a81-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89a81-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="89a81-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89a81-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a81-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89a81-114">See also</span></span>

- [<span data-ttu-id="89a81-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a81-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
