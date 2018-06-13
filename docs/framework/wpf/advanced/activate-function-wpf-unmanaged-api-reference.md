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
ms.openlocfilehash: 4931f64a525f14ad5b0b69c582a81cd15d98e541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539052"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="0beab-102">Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0beab-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="0beab-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0beab-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="0beab-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Windows.</span><span class="sxs-lookup"><span data-stu-id="0beab-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0beab-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0beab-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0beab-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0beab-106">Parameters</span></span>  
 <span data-ttu-id="0beab-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="0beab-107">pParameters</span></span>  
 <span data-ttu-id="0beab-108">Ein Zeiger auf das Fenster Aktivierungsparameter.</span><span class="sxs-lookup"><span data-stu-id="0beab-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="0beab-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="0beab-109">ppInner</span></span>  
 <span data-ttu-id="0beab-110">Ein Zeiger auf die Adresse eines Puffers Einzelelement-, die einen Zeiger auf ein <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0beab-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0beab-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0beab-111">Requirements</span></span>  
 <span data-ttu-id="0beab-112">**Plattformen:** finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0beab-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0beab-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="0beab-113">**DLL:**</span></span>  
  
 <span data-ttu-id="0beab-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="0beab-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="0beab-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="0beab-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="0beab-116">**.NET Framework-Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0beab-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0beab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0beab-117">See Also</span></span>  
 [<span data-ttu-id="0beab-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="0beab-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
