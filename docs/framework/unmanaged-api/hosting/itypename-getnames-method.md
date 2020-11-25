---
title: ITypeName::GetNames-Methode
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
ms.openlocfilehash: 91e73f8e3d2e3c372d3fe1c4fd4fccf6ff67b363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727808"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="21706-102">ITypeName::GetNames-Methode</span><span class="sxs-lookup"><span data-stu-id="21706-102">ITypeName::GetNames Method</span></span>

<span data-ttu-id="21706-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="21706-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21706-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21706-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="21706-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21706-105">Requirements</span></span>  

 <span data-ttu-id="21706-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21706-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21706-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="21706-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21706-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="21706-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21706-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21706-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21706-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21706-110">See also</span></span>

- [<span data-ttu-id="21706-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="21706-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
