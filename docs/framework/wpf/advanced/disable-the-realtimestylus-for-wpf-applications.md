---
title: Deaktivieren Sie den RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186085"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="643b5-102">Deaktivieren des RealTimeStylus für WPF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="643b5-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="643b5-103">Windows Presentation Foundation (WPF) hat Unterstützung für die Verarbeitung von Windows 7-Touch-Eingaben integriert.</span><span class="sxs-lookup"><span data-stu-id="643b5-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="643b5-104">Die Unterstützung erfolgt über die Echtzeiteingabe des Eingabestifts der Tablettplattform als <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>und <xref:System.Windows.UIElement.OnStylusMove%2A> über Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="643b5-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="643b5-105">Windows 7 bietet auch Multi-Touch-Eingaben als Win32-WM_TOUCH Fensternachrichten.</span><span class="sxs-lookup"><span data-stu-id="643b5-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="643b5-106">Diese beiden APIs schließen sich für dieselbe HWND gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="643b5-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="643b5-107">Durch aktivierende Touch-Eingabe über die Tablet-Plattform (Standard für WPF-Anwendungen) wird WM_TOUCH Nachrichten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="643b5-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="643b5-108">Um WM_TOUCH zum Empfangen von Touchnachrichten aus einem WPF-Fenster zu verwenden, müssen Sie daher die integrierte Stiftunterstützung in WPF deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="643b5-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="643b5-109">Dies gilt in einem Szenario, z. B. in einem WPF-Fenster, in dem eine Komponente gehostet wird, die WM_TOUCH verwendet.</span><span class="sxs-lookup"><span data-stu-id="643b5-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="643b5-110">Um das WPF-Hören von Stifteingabe zu deaktivieren, entfernen Sie alle Tablett-Unterstützungen, die vom WPF-Fenster hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="643b5-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="643b5-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="643b5-111">Example</span></span>  
 <span data-ttu-id="643b5-112">Der folgende Beispielcode zeigt, wie Sie die standardmäßige Unterstützung der Tablettplattform mithilfe von Reflektion entfernen.</span><span class="sxs-lookup"><span data-stu-id="643b5-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
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
  
## <a name="see-also"></a><span data-ttu-id="643b5-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="643b5-113">See also</span></span>

- [<span data-ttu-id="643b5-114">Abfangen von Tablettstifteingaben</span><span class="sxs-lookup"><span data-stu-id="643b5-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
