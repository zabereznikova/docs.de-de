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
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616449"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="f8400-102">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="f8400-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="f8400-103">Erstellt ein [ICeeFileGen](iceefilegen-class.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="f8400-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="f8400-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f8400-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8400-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8400-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8400-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8400-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="f8400-107">vorgenommen Ein Zeiger auf die Adresse eines neuen- `ICeeFileGen` Objekts.</span><span class="sxs-lookup"><span data-stu-id="f8400-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8400-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8400-108">Return Value</span></span>  
 <span data-ttu-id="f8400-109">Diese Methode gibt com-Standard Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="f8400-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8400-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8400-110">Remarks</span></span>  
 <span data-ttu-id="f8400-111">Das- `ICeeFileGen` Objekt wird verwendet, um Common Language Runtime (CLR) portable ausführbare Dateien (PE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8400-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="f8400-112">Nennen Sie die [DestroyICeeFileGen](destroyiceefilegen-function.md) -Funktion, um das Objekt zu zerstören, `ICeeFileGen` Wenn es beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f8400-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8400-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8400-113">Requirements</span></span>  
 <span data-ttu-id="f8400-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8400-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8400-115">**Header:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="f8400-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="f8400-116">**Bibliothek:** Mscorpe. dll</span><span class="sxs-lookup"><span data-stu-id="f8400-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="f8400-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8400-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8400-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8400-118">See also</span></span>

- [<span data-ttu-id="f8400-119">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f8400-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
