---
title: Deaktivieren des RealTimeStylus für WPF-Anwendungen
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 7b97a451c52b72ee1ddcec5c58e1848a0b10fb7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616909"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="f6c0e-102">Deaktivieren des RealTimeStylus für WPF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f6c0e-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="f6c0e-103">Windows Presentation Foundation (WPF) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7-Touch-Punkts. Die Unterstützung wird über die Tablet-Plattform in Echtzeit-Stylus-Eingabe als <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, und <xref:System.Windows.UIElement.OnStylusMove%2A> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="f6c0e-104">Windows 7 bietet außerdem Multitouch-Eingaben als Win32-WM_TOUCH-Windows-Meldungen.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="f6c0e-105">Diese beiden APIs gegenseitig auf demselben HWND.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="f6c0e-106">Aktivierung Fingereingabe über die Tablet-Plattform (die Standardeinstellung für WPF-Anwendungen) deaktiviert die WM_TOUCH-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="f6c0e-107">Um WM_TOUCH verwenden, um die Touch-Nachrichten von einem WPF-Fenster zu erhalten, müssen Sie daher die integrierten stiftunterstützung in WPF deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="f6c0e-108">Dies gilt in einem Szenario wie z. B. ein WPF-Fenster, das Hosten einer Komponente, die WM_TOUCH verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="f6c0e-109">Um WPF-nastala chyba vstupu Überwachung zu deaktivieren, entfernen Sie alle Tablet-Unterstützung, die von der WPF-Fenster hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6c0e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6c0e-110">Example</span></span>  
 <span data-ttu-id="f6c0e-111">Der folgende Beispielcode veranschaulicht die standardunterstützung für Tablet-Plattform zu entfernen, indem Sie mithilfe von Reflektion.</span><span class="sxs-lookup"><span data-stu-id="f6c0e-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6c0e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6c0e-112">See also</span></span>
- [<span data-ttu-id="f6c0e-113">Abfangen von Tablettstifteingaben</span><span class="sxs-lookup"><span data-stu-id="f6c0e-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
