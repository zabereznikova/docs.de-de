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
ms.openlocfilehash: 215f6ff727b814e7e7d7c708c29a8c5221f5797f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575981"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="eacd6-102">CreateIDispatchSTAForwarder-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eacd6-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="eacd6-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eacd6-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="eacd6-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Threads und Windows.</span><span class="sxs-lookup"><span data-stu-id="eacd6-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacd6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eacd6-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eacd6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eacd6-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="eacd6-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eacd6-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="eacd6-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="eacd6-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="eacd6-109">Ein Zeiger auf ein `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eacd6-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="eacd6-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="eacd6-110">ppForwarder</span></span>  
 <span data-ttu-id="eacd6-111">Ein Zeiger auf die Adresse einer `IDispatch` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eacd6-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eacd6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eacd6-112">Requirements</span></span>  
 <span data-ttu-id="eacd6-113">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eacd6-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eacd6-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="eacd6-114">**DLL:**</span></span>  
  
 <span data-ttu-id="eacd6-115">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="eacd6-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="eacd6-116">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="eacd6-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="eacd6-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eacd6-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacd6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eacd6-118">See also</span></span>
- [<span data-ttu-id="eacd6-119">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="eacd6-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
