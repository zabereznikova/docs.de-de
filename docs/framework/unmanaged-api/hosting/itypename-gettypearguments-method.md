---
title: ITypeName::GetTypeArguments-Methode
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: e059cdddef7926c1359a83bc562146203724aa60
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842107"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="e2566-102">ITypeName::GetTypeArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="e2566-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="e2566-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e2566-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2566-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2566-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e2566-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2566-105">Requirements</span></span>  
 <span data-ttu-id="e2566-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2566-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2566-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e2566-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2566-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e2566-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2566-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2566-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2566-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2566-110">See also</span></span>

- [<span data-ttu-id="e2566-111">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2566-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
