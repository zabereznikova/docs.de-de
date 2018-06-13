---
title: ICeeGen::GetString-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7ac5ef95ca3705b11cfda51d7fd1aca7400abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443072"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="4276a-102">ICeeGen::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="4276a-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="4276a-103">Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4276a-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="4276a-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4276a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4276a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4276a-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4276a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4276a-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="4276a-107">[in] Die relative virtuelle Adresse der Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4276a-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="4276a-108">[out] Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4276a-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4276a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4276a-109">Requirements</span></span>  
 <span data-ttu-id="4276a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4276a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4276a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4276a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4276a-112">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4276a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4276a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4276a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4276a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4276a-114">See Also</span></span>  
 [<span data-ttu-id="4276a-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4276a-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
