---
title: Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357273"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1f04d-102">Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1f04d-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1f04d-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f04d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1f04d-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="1f04d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f04d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f04d-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f04d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f04d-106">Parameters</span></span>  
 <span data-ttu-id="1f04d-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="1f04d-107">pParameters</span></span>  
 <span data-ttu-id="1f04d-108">Ein Zeiger auf die Aktivierungsparameter des Fensters.</span><span class="sxs-lookup"><span data-stu-id="1f04d-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="1f04d-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="1f04d-109">ppInner</span></span>  
 <span data-ttu-id="1f04d-110">Ein Zeiger auf die Adresse eines Puffers, der einen Zeiger auf enthält einem Element eine <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="1f04d-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f04d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f04d-111">Requirements</span></span>  
 <span data-ttu-id="1f04d-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f04d-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f04d-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="1f04d-113">**DLL:**</span></span>  
  
 <span data-ttu-id="1f04d-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1f04d-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1f04d-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1f04d-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1f04d-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f04d-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f04d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f04d-117">See also</span></span>
- [<span data-ttu-id="1f04d-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="1f04d-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
