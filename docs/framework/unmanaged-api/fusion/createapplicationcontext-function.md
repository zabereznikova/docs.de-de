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
ms.openlocfilehash: e188fe80e770481aac02244a2c105639e4da19e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108896"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="5beff-102">CreateApplicationContext-Funktion</span><span class="sxs-lookup"><span data-stu-id="5beff-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="5beff-103">Diese Funktion unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5beff-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5beff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5beff-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5beff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5beff-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="5beff-106">in Ein Zeiger auf einen anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="5beff-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="5beff-107">vorgenommen Ein Zeiger auf einen Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="5beff-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5beff-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5beff-108">Requirements</span></span>  
 <span data-ttu-id="5beff-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5beff-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5beff-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5beff-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5beff-111">**Bibliothek:** Als Ressource in Fusion. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5beff-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="5beff-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5beff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5beff-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5beff-113">See also</span></span>

- [<span data-ttu-id="5beff-114">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5beff-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="5beff-115">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5beff-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="5beff-116">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="5beff-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
