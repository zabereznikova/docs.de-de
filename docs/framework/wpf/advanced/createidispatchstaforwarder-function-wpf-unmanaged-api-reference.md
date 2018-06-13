---
title: CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7e45d5cafa40ba147fe39888e74a67ac9f95c5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536650"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="9e349-102">CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9e349-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="9e349-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e349-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="9e349-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Threads und Windows.</span><span class="sxs-lookup"><span data-stu-id="9e349-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e349-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e349-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e349-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e349-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9e349-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9e349-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="9e349-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="9e349-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="9e349-109">Ein Zeiger auf eine `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9e349-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="9e349-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="9e349-110">ppForwarder</span></span>  
 <span data-ttu-id="9e349-111">Ein Zeiger auf die Adresse einer `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9e349-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e349-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e349-112">Requirements</span></span>  
 <span data-ttu-id="9e349-113">**Plattformen:** finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e349-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e349-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="9e349-114">**DLL:**</span></span>  
  
 <span data-ttu-id="9e349-115">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="9e349-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="9e349-116">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="9e349-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="9e349-117">**.NET Framework-Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e349-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e349-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e349-118">See Also</span></span>  
 [<span data-ttu-id="9e349-119">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="9e349-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
