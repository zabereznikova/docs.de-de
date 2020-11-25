---
title: GetAppIdAuthority-Funktion
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: 5e731ac1c652b8b4505073a3a10463ae0ce21ac0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724493"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="15c5e-102">GetAppIdAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="15c5e-102">GetAppIdAuthority Function</span></span>

<span data-ttu-id="15c5e-103">Ruft einen Zeiger auf eine [IAppIdAuthority](iappidauthority-interface.md) -Instanz ab, die Schlüssel für Anwendungs Identitäten und-Verweise verwaltet.</span><span class="sxs-lookup"><span data-stu-id="15c5e-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15c5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="15c5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15c5e-105">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="15c5e-106">vorgenommen Der zurückgegebene `IAppIdAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="15c5e-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c5e-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15c5e-107">Requirements</span></span>  

 <span data-ttu-id="15c5e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15c5e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15c5e-109">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="15c5e-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="15c5e-110">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15c5e-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c5e-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15c5e-111">See also</span></span>

- [<span data-ttu-id="15c5e-112">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15c5e-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="15c5e-113">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="15c5e-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
