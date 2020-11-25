---
title: GetIdentityAuthority-Funktion
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: e9631211993afbfe968c7122828251746f15c3f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732124"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="d1eaf-102">GetIdentityAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="d1eaf-102">GetIdentityAuthority Function</span></span>

<span data-ttu-id="d1eaf-103">Ruft einen Zeiger auf eine [IIdentityAuthority](iidentityauthority-interface.md) -Instanz ab, die Schlüssel für Code Objekte verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1eaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1eaf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1eaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1eaf-105">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="d1eaf-106">vorgenommen Der zurückgegebene `IIdentityAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1eaf-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d1eaf-107">Requirements</span></span>  

 <span data-ttu-id="d1eaf-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1eaf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1eaf-109">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d1eaf-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d1eaf-110">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1eaf-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1eaf-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1eaf-111">See also</span></span>

- [<span data-ttu-id="d1eaf-112">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1eaf-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="d1eaf-113">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="d1eaf-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
