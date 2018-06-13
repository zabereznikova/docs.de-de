---
title: CreateApplicationContext-Funktion
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80012d030d0ea51ab3d150a7fd346b78e29dbde5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430099"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="f18bf-102">CreateApplicationContext-Funktion</span><span class="sxs-lookup"><span data-stu-id="f18bf-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="f18bf-103">Diese Funktion unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f18bf-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f18bf-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f18bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f18bf-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="f18bf-106">[in] Ein Zeiger auf einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="f18bf-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="f18bf-107">[out] Ein Zeiger auf einen Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="f18bf-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f18bf-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f18bf-108">Requirements</span></span>  
 <span data-ttu-id="f18bf-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f18bf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f18bf-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f18bf-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f18bf-111">**Bibliothek:** als Ressource in Fusion.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f18bf-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="f18bf-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f18bf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f18bf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f18bf-113">See Also</span></span>  
 [<span data-ttu-id="f18bf-114">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f18bf-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="f18bf-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="f18bf-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="f18bf-116">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="f18bf-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
