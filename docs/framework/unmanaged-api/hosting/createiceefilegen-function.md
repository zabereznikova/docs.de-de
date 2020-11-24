---
title: CreateICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 454cfa2dd1b676f32649050625b1074fbd776d54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673331"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="f18eb-102">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="f18eb-102">CreateICeeFileGen Function</span></span>

<span data-ttu-id="f18eb-103">Erstellt ein [ICeeFileGen](iceefilegen-class.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="f18eb-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="f18eb-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f18eb-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18eb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f18eb-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f18eb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f18eb-106">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="f18eb-107">vorgenommen Ein Zeiger auf die Adresse eines neuen- `ICeeFileGen` Objekts.</span><span class="sxs-lookup"><span data-stu-id="f18eb-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f18eb-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f18eb-108">Return Value</span></span>  

 <span data-ttu-id="f18eb-109">Diese Methode gibt com-Standard Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="f18eb-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f18eb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f18eb-110">Remarks</span></span>  

 <span data-ttu-id="f18eb-111">Das- `ICeeFileGen` Objekt wird verwendet, um Common Language Runtime (CLR) portable ausführbare Dateien (PE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f18eb-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="f18eb-112">Nennen Sie die [DestroyICeeFileGen](destroyiceefilegen-function.md) -Funktion, um das Objekt zu zerstören, `ICeeFileGen` Wenn es beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f18eb-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f18eb-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f18eb-113">Requirements</span></span>  

 <span data-ttu-id="f18eb-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f18eb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f18eb-115">**Header:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="f18eb-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="f18eb-116">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="f18eb-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="f18eb-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f18eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f18eb-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f18eb-118">See also</span></span>

- [<span data-ttu-id="f18eb-119">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f18eb-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
