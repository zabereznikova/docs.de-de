---
title: ITypeNameFactory::ParseTypeName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeNameFactory.ParseTypeName
api_location: mscoree.dll
api_type: COM
f1_keywords: ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1bb762dbf1751a32939cb1acd41e1dd2fb77ef2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="95293-102">ITypeNameFactory::ParseTypeName-Methode</span><span class="sxs-lookup"><span data-stu-id="95293-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="95293-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="95293-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95293-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95293-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="95293-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95293-105">Requirements</span></span>  
 <span data-ttu-id="95293-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95293-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95293-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95293-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95293-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="95293-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95293-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95293-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95293-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95293-110">See Also</span></span>  
 [<span data-ttu-id="95293-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="95293-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
