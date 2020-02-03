---
title: "\"RealTimeStylus\" deaktivieren"
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737940"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="2e5a7-102">Deaktivieren des RealTimeStylus für WPF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2e5a7-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="2e5a7-103">Windows Presentation Foundation (WPF) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7-Berührungs Eingaben.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="2e5a7-104">Die Unterstützung erfolgt durch die Echt Zeit Stift Eingabe der Tablet-Plattform als <xref:System.Windows.UIElement.OnStylusDown%2A>-, <xref:System.Windows.UIElement.OnStylusUp%2A>-und <xref:System.Windows.UIElement.OnStylusMove%2A>-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="2e5a7-105">Windows 7 bietet auch Multitouch-Eingaben als Win32-WM_TOUCH Fenster Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="2e5a7-106">Diese beiden APIs schließen sich gegenseitig auf demselben HWND aus.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="2e5a7-107">Aktivieren von Finger Eingaben über die Tablet-Plattform (Standard für WPF-Anwendungen) deaktiviert WM_TOUCH Meldungen.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="2e5a7-108">Daher müssen Sie die integrierte tablettstiftunterstützung in WPF deaktivieren, um WM_TOUCH zum Empfangen von Finger Eingaben von einem WPF-Fenster zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="2e5a7-109">Dies gilt für ein Szenario wie z. b. ein WPF-Fenster, in dem eine Komponente gehostet wird, die WM_TOUCH verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="2e5a7-110">Entfernen Sie alle Tablet-Unterstützung, die vom WPF-Fenster hinzugefügt wurde, um WPF zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e5a7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e5a7-111">Example</span></span>  
 <span data-ttu-id="2e5a7-112">Der folgende Beispielcode zeigt, wie die standardmäßige Unterstützung der Tablet-Plattform mithilfe von Reflektion entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="2e5a7-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e5a7-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e5a7-113">See also</span></span>

- [<span data-ttu-id="2e5a7-114">Abfangen von Tablettstifteingaben</span><span class="sxs-lookup"><span data-stu-id="2e5a7-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
