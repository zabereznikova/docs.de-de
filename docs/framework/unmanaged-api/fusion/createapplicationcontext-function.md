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
ms.openlocfilehash: d98829b29100824e5d606e23aaf287c9f6e81d69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771916"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="c39ee-102">CreateApplicationContext-Funktion</span><span class="sxs-lookup"><span data-stu-id="c39ee-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="c39ee-103">Diese Funktion unterstützt die .NET Framework-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c39ee-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c39ee-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c39ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c39ee-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="c39ee-106">[in] Ein Zeiger auf einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="c39ee-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="c39ee-107">[out] Ein Zeiger auf einem Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="c39ee-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c39ee-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c39ee-108">Requirements</span></span>  
 <span data-ttu-id="c39ee-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c39ee-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c39ee-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c39ee-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c39ee-111">**Bibliothek:** Als Ressource in Fusion.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c39ee-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="c39ee-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c39ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39ee-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c39ee-113">See also</span></span>

- [<span data-ttu-id="c39ee-114">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c39ee-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="c39ee-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="c39ee-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="c39ee-116">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="c39ee-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
