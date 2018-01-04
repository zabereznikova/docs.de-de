---
title: "Deaktivieren des RealTimeStylus für WPF-Anwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fc4ec888419e385a57216f078387f731c0ab8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="ddeca-102">Deaktivieren des RealTimeStylus für WPF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ddeca-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="ddeca-103">Windows Presentation Foundation (WPF) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7 Fingereingabe. Die Unterstützung wird über die Tablet-Plattform in Echtzeit Stifteingabe als <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, und <xref:System.Windows.UIElement.OnStylusMove%2A> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="ddeca-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="ddeca-104">Windows 7 enthält außerdem die Multi-Touch-Eingabe als Win32-WM_TOUCH fenstermeldungen.</span><span class="sxs-lookup"><span data-stu-id="ddeca-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="ddeca-105">Diese zwei APIs gegenseitig auf demselben HWND.</span><span class="sxs-lookup"><span data-stu-id="ddeca-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="ddeca-106">Aktivieren des Touch eingehende deaktiviert WM_TOUCH Nachrichten, über die Plattform (die Standardeinstellung für WPF-Anwendungen).</span><span class="sxs-lookup"><span data-stu-id="ddeca-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="ddeca-107">Um WM_TOUCH verwenden, um Touch-Nachrichten aus einem WPF-Fenster zu erhalten, müssen Sie daher die integrierten Tablettstift-Unterstützung in WPF deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ddeca-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="ddeca-108">Dies gilt in einem Szenario wie beispielsweise ein WPF-Fenster, das Hosten einer Komponente, die WM_TOUCH verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddeca-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="ddeca-109">Um WPF-Überwachung der Stifteingabe zu deaktivieren, entfernen Sie alle Tablet-Unterstützung durch das WPF-Fenster hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ddeca-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddeca-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddeca-110">Example</span></span>  
 <span data-ttu-id="ddeca-111">Der folgende Beispielcode veranschaulicht die plattformunterstützung für Standard-Tablet zu entfernen, indem Sie über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ddeca-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddeca-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddeca-112">See Also</span></span>  
 [<span data-ttu-id="ddeca-113">Abfangen von Tablettstifteingaben</span><span class="sxs-lookup"><span data-stu-id="ddeca-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
