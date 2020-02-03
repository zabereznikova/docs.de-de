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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deaktivieren des RealTimeStylus für WPF-Anwendungen

Windows Presentation Foundation (WPF) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7-Berührungs Eingaben. Die Unterstützung erfolgt durch die Echt Zeit Stift Eingabe der Tablet-Plattform als <xref:System.Windows.UIElement.OnStylusDown%2A>-, <xref:System.Windows.UIElement.OnStylusUp%2A>-und <xref:System.Windows.UIElement.OnStylusMove%2A>-Ereignisse. Windows 7 bietet auch Multitouch-Eingaben als Win32-WM_TOUCH Fenster Nachrichten. Diese beiden APIs schließen sich gegenseitig auf demselben HWND aus. Aktivieren von Finger Eingaben über die Tablet-Plattform (Standard für WPF-Anwendungen) deaktiviert WM_TOUCH Meldungen. Daher müssen Sie die integrierte tablettstiftunterstützung in WPF deaktivieren, um WM_TOUCH zum Empfangen von Finger Eingaben von einem WPF-Fenster zu verwenden. Dies gilt für ein Szenario wie z. b. ein WPF-Fenster, in dem eine Komponente gehostet wird, die WM_TOUCH verwendet.  
  
 Entfernen Sie alle Tablet-Unterstützung, die vom WPF-Fenster hinzugefügt wurde, um WPF zu deaktivieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt, wie die standardmäßige Unterstützung der Tablet-Plattform mithilfe von Reflektion entfernt wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Abfangen von Tablettstifteingaben](intercepting-input-from-the-stylus.md)
