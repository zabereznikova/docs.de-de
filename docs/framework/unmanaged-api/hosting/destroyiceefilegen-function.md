---
title: DestroyICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 495d84470c559df13ea64b63dd00582f4335d4e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673177"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="4a9af-102">DestroyICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="4a9af-102">DestroyICeeFileGen Function</span></span>

<span data-ttu-id="4a9af-103">Zerstört ein [ICeeFileGen](iceefilegen-class.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="4a9af-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="4a9af-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4a9af-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a9af-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a9af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a9af-106">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="4a9af-107">in Das `ICeeFileGen` Objekt, das zerstört werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a9af-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a9af-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4a9af-108">Return Value</span></span>  

 <span data-ttu-id="4a9af-109">Diese Methode gibt com-Standard Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="4a9af-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a9af-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a9af-110">Remarks</span></span>  

 <span data-ttu-id="4a9af-111">`DestroyICeeFileGen` zerstört das-Objekt, das `ICeeFileGen` von der Funktion " [kreateiceefilegen](createiceefilegen-function.md) " erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a9af-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a9af-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a9af-112">Requirements</span></span>  

 <span data-ttu-id="4a9af-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a9af-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9af-114">**Header:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="4a9af-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="4a9af-115">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="4a9af-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="4a9af-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a9af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9af-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a9af-117">See also</span></span>

- [<span data-ttu-id="4a9af-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4a9af-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
