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
  
Ab Windows Vista ermöglicht Windows Benutzern das Ändern der dpi-Einstellung (dots per inch), sodass die meisten Elemente der Benutzeroberfläche (UI) auf dem Bildschirm größer erscheinen. Obwohl dieses Feature seit langem in Windows verfügbar ist, musste die Skalierung in früheren Versionen von Anwendungen implementiert werden. Ab Windows Vista führt die Desktopfenster-Manager eine Standard Skalierung für alle Anwendungen aus, die ihre eigene Skalierung nicht verarbeiten. Benutzeroberflächenautomatisierungs-Clientanwendungen müssen dieses Feature berücksichtigen.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Skalierung in Windows Vista  
 Die dpi-Standardeinstellung ist 96. Dies bedeutet, dass 96 Pixel eine Breite oder Höhe von einem einzelnen Zoll belegen. Das genaue Maß für ein „Zoll“ ist abhängig von der Größe und der physischen Auflösung des Monitors. Auf einem Monitor mit einer Breite von 12 Zoll bei einer horizontalen Auflösung von 1280 Pixel erstreckt sich eine horizontale Linie von 96 Pixeln beispielsweise über etwas 9/10 eines Zolls.  
  
 Das Ändern der dpi-Einstellung ist nicht dasselbe wie das Ändern der Bildschirmauflösung. Bei der DPI-Skalierung bleibt die Anzahl der physischen Pixel auf dem Bildschirm unverändert. Die Skalierung wird jedoch auf die Größe und Position der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente angewendet. Diese Skalierung kann vom Desktopfenster-Manager (DWM) für den Desktop und für Anwendungen automatisch durchgeführt werden , die nicht ausdrücklich danach verlangen, nicht skaliert zu werden.  
  
 Wenn der Benutzer den Skalierungsfaktor auf 120 DPI festlegt, wird ein vertikaler oder horizontaler Zoll auf dem Bildschirm um 25 Prozent vergrößert. Alle Dimensionen werden entsprechend skaliert. Der Offset eines Anwendungsfensters vom oberen und linken Rand des Bildschirms wird um 25 Prozent erhöht. Wenn die Anwendungs Skalierung aktiviert ist und die Anwendung nicht mit dpi-Werten kompatibel ist, wird die Größe des Fensters im selben Verhältnis zusammen mit den Offsets und Größen aller darin enthaltenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente vergrößert.  
  
> [!NOTE]
> Standardmäßig führt der DWM keine Skalierung für Anwendungen ohne dpi-Unterstützung durch, wenn der Benutzer den dpi-Wert auf 120 festlegt, er aber ausführt, wenn der dpi-Wert auf einen benutzerdefinierten Wert von 144 oder höher festgelegt ist. Das Standardverhalten kann vom Benutzer jedoch außer Kraft gesetzt werden.  
  
 Die Bildschirmskalierung stellt an Anwendungen neue Herausforderungen, die sich in irgendeiner Weise mit Bildschirmkoordinaten befassen. Der Bildschirm enthält jetzt zwei Koordinatensysteme: ein physisches und ein logisches. Die physischen Koordinaten eines Punkts stellen den tatsächlichen Offset in Pixeln vom oberen linken Rand des Ursprungs dar. Die logischen Koordinaten sind die Offsets, die sich ergeben würden, wenn die Pixel selbst skaliert würden.  
  
 Angenommen, Sie entwerfen ein Dialogfeld mit einer Schaltfläche an den Koordinaten (100, 48). Wenn dieses Dialogfeld mit dem 96-Standard dpi angezeigt wird, befindet sich die Schaltfläche an den physischen Koordinaten von (100, 48). Bei 120 dpi befindet er sich an physischen Koordinaten von (125, 60). Aber die logischen Koordinaten sind bei jeder dpi-Einstellung identisch: (100, 48).  
  
 Logische Koordinaten sind wichtig, da Sie das Verhalten des Betriebssystems und der Anwendungen unabhängig von der dpi-Einstellung konsistent machen. <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> gibt z. B. normalerweise die logischen Koordinaten zurück. Wenn Sie den Cursor über ein Element in einem Dialogfeld bewegen, werden unabhängig von der dpi-Einstellung dieselben Koordinaten zurückgegeben. Wenn Sie ein Steuerelement bei (100, 100) zeichnen, wird es auf diese logischen Koordinaten gezeichnet und nimmt dieselbe relative Position bei jeder dpi-Einstellung an.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Skalierung in Benutzeroberflächenautomatisierungs-Clients  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-API verwendet keine logischen Koordinaten. Die folgenden Methoden und Eigenschaften geben entweder physische Koordinaten zurück oder verwenden sie als Parameter.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 Standardmäßig ist eine Benutzeroberflächenautomatisierungs-Client Anwendung, die in einer nicht-96-dpi-Umgebung ausgeführt wird, nicht in der Lage, von diesen Methoden und Eigenschaften die richtigen Ergebnisse zu erhalten. Da die Cursorposition z. B. in logischen Koordinaten angegeben wird, kann der Client diese Koordinaten nicht einfach an <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> übergeben, um das Element abzurufen, das sich unter dem Cursor befindet. Darüber hinaus ist die Anwendung nicht in der Lage, Fenster außerhalb seines Clientbereichs ordnungsgemäß zu platzieren.  
  
 Die Lösung besteht aus zwei Teilen.  
  
1. Legen Sie für die Client Anwendung zunächst dpi-fähig. Rufen Sie dazu die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `SetProcessDPIAware` beim Start auf. Die folgende Deklaration stellt diese Funktion in verwaltetem Code zur Verfügung.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Diese Funktion macht den gesamten Prozess dpi-fähig, was bedeutet, dass alle Fenster, die dem Prozess angehören, nicht skaliert werden. Im [highheller-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)befinden sich beispielsweise die vier Fenster, die das Hervorhebungs Rechteck bilden, an den physischen Koordinaten, die von der Benutzeroberflächen Automatisierung bezogen werden, nicht auf die logischen Koordinaten. Wenn das Beispiel nicht dpi-fähig wäre, würde die Hervorhebung an den logischen Koordinaten auf dem Desktop gezeichnet werden, was zu einer falschen Platzierung in einer nicht-96-dpi-Umgebung führen würde.  
  
2. Rufen Sie die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `GetPhysicalCursorPos`auf, um Cursorkoordinaten abzurufen. Im folgenden Beispiel wird das Deklarieren und Verwenden dieser Funktion veranschaulicht.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> Verwenden Sie nicht <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Das Verhalten dieser Eigenschaft außerhalb der Clientfenster in einer skalierten Umgebung ist nicht definiert.  
  
 Wenn Ihre Anwendung eine direkte prozessübergreifende Kommunikation mit nicht dpi-fähigen Anwendungen ausführt, haben Sie möglicherweise eine Konvertierung zwischen logischen und physischen Koordinaten mithilfe der [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] Funktionen `PhysicalToLogicalPoint` und `LogicalToPhysicalPoint`durchführen.  
  
## <a name="see-also"></a>Siehe auch

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
