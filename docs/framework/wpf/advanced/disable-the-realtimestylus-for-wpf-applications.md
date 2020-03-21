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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deaktivieren des RealTimeStylus für WPF-Anwendungen

Windows Presentation Foundation (WPF) hat Unterstützung für die Verarbeitung von Windows 7-Touch-Eingaben integriert. Die Unterstützung erfolgt über die Echtzeiteingabe des Eingabestifts der Tablettplattform als <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>und <xref:System.Windows.UIElement.OnStylusMove%2A> über Ereignisse. Windows 7 bietet auch Multi-Touch-Eingaben als Win32-WM_TOUCH Fensternachrichten. Diese beiden APIs schließen sich für dieselbe HWND gegenseitig aus. Durch aktivierende Touch-Eingabe über die Tablet-Plattform (Standard für WPF-Anwendungen) wird WM_TOUCH Nachrichten deaktiviert. Um WM_TOUCH zum Empfangen von Touchnachrichten aus einem WPF-Fenster zu verwenden, müssen Sie daher die integrierte Stiftunterstützung in WPF deaktivieren. Dies gilt in einem Szenario, z. B. in einem WPF-Fenster, in dem eine Komponente gehostet wird, die WM_TOUCH verwendet.  
  
 Um das WPF-Hören von Stifteingabe zu deaktivieren, entfernen Sie alle Tablett-Unterstützungen, die vom WPF-Fenster hinzugefügt werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt, wie Sie die standardmäßige Unterstützung der Tablettplattform mithilfe von Reflektion entfernen.  
  
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
