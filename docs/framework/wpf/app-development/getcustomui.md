---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991380"
---
# <a name="getcustomui"></a><span data-ttu-id="fe31c-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="fe31c-102">GetCustomUI</span></span>
<span data-ttu-id="fe31c-103">Wird von "PresentationHost. exe" aufgerufen, um beim implementieren benutzerdefinierte Status-und Fehlermeldungen vom Host zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe31c-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe31c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe31c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe31c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe31c-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="fe31c-106">vorgenommen Ein Zeiger auf die Assembly, die die vom Host bereitgestellte Status-Benutzeroberfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="fe31c-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="fe31c-107">vorgenommen Der Name der Klasse, die die vom Host bereitgestellte Status-Benutzeroberfläche ist, [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] vorzugsweise <xref:System.Windows.Controls.Page> eine Datei mit dem Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="fe31c-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="fe31c-108">Diese Klasse befindet sich in der Assembly, die von `pwzProgressAssemblyName`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe31c-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="fe31c-109">vorgenommen Ein Zeiger auf die Assembly, die die vom Host bereitgestellte Fehler Benutzeroberfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="fe31c-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="fe31c-110">vorgenommen Der Name der Klasse, die die vom Host bereitgestellte Fehler Benutzeroberfläche ist, vorzugsweise eine XAML <xref:System.Windows.Controls.Page> -Datei mit dem Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="fe31c-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="fe31c-111">Diese Klasse befindet sich in der Assembly, die von `pwzErrorAssemblyName`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe31c-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fe31c-112">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe31c-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="fe31c-113">HRESULT: Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fe31c-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe31c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe31c-114">Remarks</span></span>  
 <span data-ttu-id="fe31c-115">Eine Host Anwendung kann über ein bestimmtes Design verfügen, das von den Standardbenutzer Oberflächen von PresentationHost. exe möglicherweise nicht konform ist.</span><span class="sxs-lookup"><span data-stu-id="fe31c-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="fe31c-116">Wenn dies der Fall ist, kann die Host Anwendung [GetCustomUI](getcustomui.md) implementieren, um den Fortschritt und Fehler Benutzerschnittstellen an PresentationHost. exe zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe31c-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="fe31c-117">"PresentationHost. exe" ruft immer " [GetCustomUI](getcustomui.md) " auf, bevor die Standardbenutzer Oberflächen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe31c-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="fe31c-118">Diese Funktion wird während der PresentationHost-Initialisierung einmal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fe31c-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe31c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe31c-119">See also</span></span>

- [<span data-ttu-id="fe31c-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="fe31c-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
