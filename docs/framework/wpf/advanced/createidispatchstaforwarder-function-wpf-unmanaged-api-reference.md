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
ms.openlocfilehash: 1a19b7699c7a9e2b663149ea31bccb67189e68c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487823"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="97376-102">CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="97376-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="97376-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97376-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="97376-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Threads und Windows.</span><span class="sxs-lookup"><span data-stu-id="97376-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97376-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97376-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="97376-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="97376-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="97376-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97376-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="97376-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="97376-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="97376-109">Ein Zeiger auf ein `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="97376-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="97376-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="97376-110">ppForwarder</span></span>  
 <span data-ttu-id="97376-111">Ein Zeiger auf die Adresse einer `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="97376-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97376-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97376-112">Requirements</span></span>  
 <span data-ttu-id="97376-113">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97376-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97376-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="97376-114">**DLL:**</span></span>  
  
 <span data-ttu-id="97376-115">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="97376-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="97376-116">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="97376-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="97376-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97376-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97376-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97376-118">See also</span></span>
- [<span data-ttu-id="97376-119">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="97376-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
