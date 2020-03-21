---
title: CreateIDispatchSTAForwarder-Funktion - Nicht verwalteter WPF-API-Verweis
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174718"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="26b6a-102">CreateIDispatchSTAForwarder-Funktion (WPF-Referenz für nicht verwaltete API)</span><span class="sxs-lookup"><span data-stu-id="26b6a-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="26b6a-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und ist nicht für die direkte Verwendung aus ihrem Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="26b6a-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="26b6a-104">Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Thread- und Windows-Verwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="26b6a-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b6a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26b6a-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="26b6a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="26b6a-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="26b6a-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="26b6a-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="26b6a-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="26b6a-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="26b6a-109">Ein Zeiger auf `IDispatch` eine Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="26b6a-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="26b6a-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="26b6a-110">ppForwarder</span></span>  
 <span data-ttu-id="26b6a-111">Ein Zeiger auf die `IDispatch` Adresse einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="26b6a-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b6a-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26b6a-112">Requirements</span></span>  
 <span data-ttu-id="26b6a-113">**Plattformen:** Siehe [.NET Framework Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26b6a-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b6a-114">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="26b6a-114">**DLL:**</span></span>  
  
 <span data-ttu-id="26b6a-115">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="26b6a-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="26b6a-116">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="26b6a-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="26b6a-117">**.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b6a-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b6a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26b6a-118">See also</span></span>

- [<span data-ttu-id="26b6a-119">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="26b6a-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
