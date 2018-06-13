---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: ff68c30c4e58cebb70c59352593d7b084413dce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548645"
---
# <a name="getcustomui"></a><span data-ttu-id="1b3b4-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="1b3b4-102">GetCustomUI</span></span>
<span data-ttu-id="1b3b4-103">Wird vom PresentationHost.exe abzurufenden benutzerdefinierten Status- und Fehlermeldungen vom Host aufgerufen, wenn implementiert.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b3b4-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b3b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b3b4-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="1b3b4-106">[out] Ein Zeiger auf die Assembly, die den Host bereitgestellte tasksequenzstatus-Benutzeroberfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="1b3b4-107">[out] Der Name der Klasse, die den Host bereitgestellte tasksequenzstatus-Benutzeroberfläche, vorzugsweise ist ein [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] -Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="1b3b4-108">Diese Klasse befindet sich in der Assembly, die von angegeben wird `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="1b3b4-109">[out] Ein Zeiger auf die Assembly, die Fehler Host bereitgestellte Benutzeroberfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="1b3b4-110">[out] Der Name der Klasse, die der Host angegebene Benutzer ist Schnittstelle vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="1b3b4-111">Diese Klasse befindet sich in der Assembly, die von angegeben wird `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1b3b4-112">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b3b4-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="1b3b4-113">HRESULT: ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b3b4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b3b4-114">Remarks</span></span>  
 <span data-ttu-id="1b3b4-115">Eine Anwendung möglicherweise ein bestimmtes Design, dem nicht PresentationHost.exe des standardmäßigen Benutzeroberflächen entsprechen können.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="1b3b4-116">Wenn dies der Fall ist, kann die hostanwendung implementieren [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) Status- und Fehlerinformationen von Benutzeroberflächen für PresentationHost.exe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="1b3b4-117">Rufen Sie PresentationHost.exe wird immer [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) vor der Verwendung der standardmäßigen Benutzeroberflächen.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="1b3b4-118">Diese Funktion wird einmal während der Initialisierung von PresentationHost aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1b3b4-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3b4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b3b4-119">See Also</span></span>  
 [<span data-ttu-id="1b3b4-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="1b3b4-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
