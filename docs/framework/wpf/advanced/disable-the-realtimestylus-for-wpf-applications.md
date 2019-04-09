---
title: Deaktivieren des RealTimeStylus für WPF-Anwendungen
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124682"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deaktivieren des RealTimeStylus für WPF-Anwendungen
Windows Presentation Foundation (WPF) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7-Touch-Punkts. Die Unterstützung wird über die Tablet-Plattform in Echtzeit-Stylus-Eingabe als <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, und <xref:System.Windows.UIElement.OnStylusMove%2A> Ereignisse. Windows 7 bietet außerdem Multitouch-Eingaben als Win32-WM_TOUCH-Windows-Meldungen. Diese beiden APIs gegenseitig auf demselben HWND. Aktivierung Fingereingabe über die Tablet-Plattform (die Standardeinstellung für WPF-Anwendungen) deaktiviert die WM_TOUCH-Nachrichten. Um WM_TOUCH verwenden, um die Touch-Nachrichten von einem WPF-Fenster zu erhalten, müssen Sie daher die integrierten stiftunterstützung in WPF deaktivieren. Dies gilt in einem Szenario wie z. B. ein WPF-Fenster, das Hosten einer Komponente, die WM_TOUCH verwendet.  
  
 Um WPF-nastala chyba vstupu Überwachung zu deaktivieren, entfernen Sie alle Tablet-Unterstützung, die von der WPF-Fenster hinzugefügt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode veranschaulicht die standardunterstützung für Tablet-Plattform zu entfernen, indem Sie mithilfe von Reflektion.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Abfangen von Tablettstifteingaben](intercepting-input-from-the-stylus.md)
