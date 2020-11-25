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
ms.openlocfilehash: bcc1cb2755c4c0a2beb0829ce58b921f073f63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727782"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="23558-102">ITypeName::GetTypeArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="23558-102">ITypeName::GetTypeArguments Method</span></span>

<span data-ttu-id="23558-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="23558-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23558-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23558-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="23558-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23558-105">Requirements</span></span>  

 <span data-ttu-id="23558-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23558-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23558-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="23558-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23558-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23558-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23558-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23558-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23558-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23558-110">See also</span></span>

- [<span data-ttu-id="23558-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="23558-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
