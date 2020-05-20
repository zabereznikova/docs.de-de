---
title: FExecuteInAppDomainCallback-Funktionszeiger
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616150"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="64873-102">FExecuteInAppDomainCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="64873-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="64873-103">Verweist auf eine Funktion, die vom Common Language Runtime (CLR) aufgerufen wird, um verwalteten Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="64873-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="64873-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="64873-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64873-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="64873-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64873-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="64873-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="64873-107">in Ein Zeiger auf den nicht transparenten vom Aufrufer zugewiesenen Speicher, der den verwalteten Code enthält, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="64873-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="64873-108">Die Zuordnung und die Lebensdauer dieses Speichers werden vom Aufrufer (d. h. der CLR) gesteuert.</span><span class="sxs-lookup"><span data-stu-id="64873-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="64873-109">Dabei handelt es sich nicht um CLR-verwalteten Heap Speicher.</span><span class="sxs-lookup"><span data-stu-id="64873-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64873-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64873-110">Requirements</span></span>  
 <span data-ttu-id="64873-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64873-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64873-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="64873-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64873-113">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="64873-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="64873-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64873-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64873-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64873-115">See also</span></span>

- [<span data-ttu-id="64873-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="64873-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
