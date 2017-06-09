---
title: "Deaktivieren des RealTimeStylus f&#252;r WPF-Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Deaktivieren des RealTimeStylus f&#252;r WPF-Anwendungen
Windows Presentation Foundation \(WPF\) verfügt über integrierte Unterstützung für die Verarbeitung von Windows 7 Fingereingabe. Die Unterstützung wird über die Echtzeit\-Tablettstifteingabe der Plattform als die Ereignisse  <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A> und <xref:System.Windows.UIElement.OnStylusMove%2A> bereitgestellt.  Außerdem stellt Windows 7 die Mehrfingereingabeeingabe als Win32\-WM\_TOUCH\-Fenstermeldungen bereit.  Diese beiden APIs schließen sich gegenseitig auf demselben HWND aus.  Die Aktivierung der Fingereingabe über die Tablet\-Plattform\(der Standard für WPF\-Anwendungen\) deaktiviert WM\_TOUCH\-Meldungen.  Um WM\_TOUCH für den Empfang von Fingereingabemeldungen aus einem WPF\-Fenster zu verwenden, müssen Sie daher die  integrierte Tablettstiftunterstützung in WPF deaktivieren.  Dies gilt für ein Szenario, wie z. B. ein WPF\-Fenster, das eine Komponente hostet, die WM\_TOUCH verwendet.  
  
 Um die WPF\-Überwachung der Tablettstifteingabe zu deaktivieren, entfernen Sie jede durch das WPF\-Fenster hinzugefügte Tablet\-Unterstützung.  
  
## Beispiel  
 Im folgenden Beispielcode wird gezeigt, wie die Standardunterstützung für Tablet\-Plattformen durch Reflektion entfernt wird.  
  
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
  
## Siehe auch  
 [Abfangen von Tablettstifteingaben](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)