---
title: Funktion "kreateidispatchstaforwarder"-Referenz zur nicht verwalteten WPF-API
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738029"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a34a8-102">Funktion "kreateidispatchstaforwarder" (Referenz zur nicht verwalteten WPF-API)</span><span class="sxs-lookup"><span data-stu-id="a34a8-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a34a8-103">Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a34a8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a34a8-104">Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Thread-und Windows-Verwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a34a8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a34a8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a34a8-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a34a8-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="a34a8-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a34a8-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a34a8-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a34a8-108">pdispatchdelegat</span><span class="sxs-lookup"><span data-stu-id="a34a8-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="a34a8-109">Ein Zeiger auf eine `IDispatch`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a34a8-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="a34a8-110">ppforwarder</span><span class="sxs-lookup"><span data-stu-id="a34a8-110">ppForwarder</span></span>  
 <span data-ttu-id="a34a8-111">Ein Zeiger auf die Adresse einer `IDispatch`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a34a8-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a34a8-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a34a8-112">Requirements</span></span>  
 <span data-ttu-id="a34a8-113">**Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a34a8-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a34a8-114">**DLL**</span><span class="sxs-lookup"><span data-stu-id="a34a8-114">**DLL:**</span></span>  
  
 <span data-ttu-id="a34a8-115">In den .NET Framework 3,0 und 3,5: presentationhostdll. dll</span><span class="sxs-lookup"><span data-stu-id="a34a8-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a34a8-116">In den .NET Framework 4 und höher: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="a34a8-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a34a8-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a34a8-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34a8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a34a8-118">See also</span></span>

- [<span data-ttu-id="a34a8-119">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="a34a8-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
