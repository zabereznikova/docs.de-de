---
title: Benutzeroberflächenautomatisierung und Bildschirmskalierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: ceab7db1f9eeb47ec020e220ec702af8181855e2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442482"
---
# <a name="ui-automation-and-screen-scaling"></a>Benutzeroberflächenautomatisierung und Bildschirmskalierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
Starting with Windows Vista, Windows enables users to change the dots per inch (dpi) setting so that most user interface (UI) elements on the screen appear larger. Although this feature has long been available in Windows, in previous versions the scaling had to be implemented by applications. Starting with Windows Vista, the Desktop Window Manager performs default scaling for all applications that do not handle their own scaling. Benutzeroberflächenautomatisierungs-Clientanwendungen müssen dieses Feature berücksichtigen.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Skalierung in Windows Vista  
 The default dpi setting is 96, which means that 96 pixels occupy a width or height of one notional inch. Das genaue Maß für ein „Zoll“ ist abhängig von der Größe und der physischen Auflösung des Monitors. Auf einem Monitor mit einer Breite von 12 Zoll bei einer horizontalen Auflösung von 1280 Pixel erstreckt sich eine horizontale Linie von 96 Pixeln beispielsweise über etwas 9/10 eines Zolls.  
  
 Changing the dpi setting is not the same as changing the screen resolution. With dpi scaling, the number of physical pixels on the screen remains the same. Die Skalierung wird jedoch auf die Größe und Position der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente angewendet. Diese Skalierung kann vom Desktopfenster-Manager (DWM) für den Desktop und für Anwendungen automatisch durchgeführt werden , die nicht ausdrücklich danach verlangen, nicht skaliert zu werden.  
  
 In effect, when the user sets the scale factor to 120 dpi, a vertical or horizontal inch on the screen becomes bigger by 25 percent. Alle Dimensionen werden entsprechend skaliert. Der Offset eines Anwendungsfensters vom oberen und linken Rand des Bildschirms wird um 25 Prozent erhöht. If application scaling is enabled and the application is not dpi-aware, the size of the window increases in the same proportion, along with the offsets and sizes of all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements it contains.  
  
> [!NOTE]
> By default, the DWM does not perform scaling for non-dpi-aware applications when the user sets the dpi to 120, but does perform it when the dpi is set to a custom value of 144 or higher. Das Standardverhalten kann vom Benutzer jedoch außer Kraft gesetzt werden.  
  
 Die Bildschirmskalierung stellt an Anwendungen neue Herausforderungen, die sich in irgendeiner Weise mit Bildschirmkoordinaten befassen. Der Bildschirm enthält jetzt zwei Koordinatensysteme: ein physisches und ein logisches. Die physischen Koordinaten eines Punkts stellen den tatsächlichen Offset in Pixeln vom oberen linken Rand des Ursprungs dar. Die logischen Koordinaten sind die Offsets, die sich ergeben würden, wenn die Pixel selbst skaliert würden.  
  
 Angenommen, Sie entwerfen ein Dialogfeld mit einer Schaltfläche an den Koordinaten (100, 48). When this dialog box is displayed at the default 96 dpi, the button is located at physical coordinates of (100, 48). At 120 dpi, it is located at physical coordinates of (125, 60). But the logical coordinates are the same at any dpi setting: (100, 48).  
  
 Logical coordinates are important, because they make the behavior of the operating system and applications consistent regardless of the dpi setting. <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> gibt z. B. normalerweise die logischen Koordinaten zurück. If you move the cursor over an element in a dialog box, the same coordinates are returned regardless of the dpi setting. If you draw a control at (100, 100), it is drawn to those logical coordinates, and will occupy the same relative position at any dpi setting.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Skalierung in Benutzeroberflächenautomatisierungs-Clients  
 The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API does not use logical coordinates. Die folgenden Methoden und Eigenschaften geben entweder physische Koordinaten zurück oder verwenden sie als Parameter.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 By default, a UI Automation client application running in a non-96- dpi environment will not be able to obtain correct results from these methods and properties. Da die Cursorposition z. B. in logischen Koordinaten angegeben wird, kann der Client diese Koordinaten nicht einfach an <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> übergeben, um das Element abzurufen, das sich unter dem Cursor befindet. Darüber hinaus ist die Anwendung nicht in der Lage, Fenster außerhalb seines Clientbereichs ordnungsgemäß zu platzieren.  
  
 Die Lösung besteht aus zwei Teilen.  
  
1. First, make the client application dpi-aware. Rufen Sie dazu die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `SetProcessDPIAware` beim Start auf. Die folgende Deklaration stellt diese Funktion in verwaltetem Code zur Verfügung.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     This function makes the entire process dpi-aware, meaning that all windows that belong to the process are unscaled. In the [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), for instance, the four windows that make up the highlight rectangle are located at the physical coordinates obtained from UI Automation, not the logical coordinates. If the sample were not dpi-aware, the highlight would be drawn at the logical coordinates on the desktop, which would result in incorrect placement in a non-96- dpi environment.  
  
2. Rufen Sie die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `GetPhysicalCursorPos`auf, um Cursorkoordinaten abzurufen. Im folgenden Beispiel wird das Deklarieren und Verwenden dieser Funktion veranschaulicht.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> Verwenden Sie nicht <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Das Verhalten dieser Eigenschaft außerhalb der Clientfenster in einer skalierten Umgebung ist nicht definiert.  
  
 If your application performs direct cross-process communication with non- dpi-aware applications, you may have convert between logical and physical coordinates by using the [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] functions `PhysicalToLogicalPoint` and `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>Siehe auch

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
