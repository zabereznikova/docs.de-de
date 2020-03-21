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
ms.openlocfilehash: 2a68a74fa6aadcaba21f142d394a1f8a3d8af371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179967"
---
# <a name="ui-automation-and-screen-scaling"></a>Benutzeroberflächenautomatisierung und Bildschirmskalierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
Ab Windows Vista ermöglicht Windows Benutzern, die Einstellung "Punkte pro Zoll" (dpi) so zu ändern, dass die meisten Benutzeroberflächenelemente auf dem Bildschirm größer angezeigt werden. Obwohl diese Funktion seit langem in Windows verfügbar ist, musste in früheren Versionen die Skalierung von Anwendungen implementiert werden. Ab Windows Vista führt der Desktopfenster-Manager eine Standardskalierung für alle Anwendungen durch, die ihre eigene Skalierung nicht verarbeiten. Benutzeroberflächenautomatisierungs-Clientanwendungen müssen dieses Feature berücksichtigen.  
  
<a name="Scaling_in_Windows_Vista"></a>
## <a name="scaling-in-windows-vista"></a>Skalierung in Windows Vista  
 Die Standard-dpi-Einstellung ist 96, was bedeutet, dass 96 Pixel eine Breite oder Höhe von einem fiktiven Zoll einnehmen. Das genaue Maß für ein „Zoll“ ist abhängig von der Größe und der physischen Auflösung des Monitors. Auf einem Monitor mit einer Breite von 12 Zoll bei einer horizontalen Auflösung von 1280 Pixel erstreckt sich eine horizontale Linie von 96 Pixeln beispielsweise über etwas 9/10 eines Zolls.  
  
 Das Ändern der dpi-Einstellung ist nicht dasselbe wie das Ändern der Bildschirmauflösung. Bei der dpi-Skalierung bleibt die Anzahl der physischen Pixel auf dem Bildschirm gleich. Die Skalierung wird jedoch auf die Größe und Position der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente angewendet. Diese Skalierung kann vom Desktopfenster-Manager (DWM) für den Desktop und für Anwendungen automatisch durchgeführt werden , die nicht ausdrücklich danach verlangen, nicht skaliert zu werden.  
  
 Wenn der Benutzer den Skalierungsfaktor auf 120 dpi festlegt, wird ein vertikaler oder horizontaler Zoll auf dem Bildschirm um 25 Prozent größer. Alle Dimensionen werden entsprechend skaliert. Der Offset eines Anwendungsfensters vom oberen und linken Rand des Bildschirms wird um 25 Prozent erhöht. Wenn die Anwendungsskalierung aktiviert ist und die Anwendung nicht dpi-fähig ist, erhöht sich die Größe [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] des Fensters im gleichen Verhältnis, zusammen mit den Offsets und Größen aller darin enthaltenen Elemente.  
  
> [!NOTE]
> Standardmäßig führt der DWM keine Skalierung für nicht-dpi-fähige Anwendungen durch, wenn der Benutzer den dpi auf 120 festlegt, sondern wenn der dpi auf einen benutzerdefinierten Wert von 144 oder höher festgelegt ist. Das Standardverhalten kann vom Benutzer jedoch außer Kraft gesetzt werden.  
  
 Die Bildschirmskalierung stellt an Anwendungen neue Herausforderungen, die sich in irgendeiner Weise mit Bildschirmkoordinaten befassen. Der Bildschirm enthält jetzt zwei Koordinatensysteme: ein physisches und ein logisches. Die physischen Koordinaten eines Punkts stellen den tatsächlichen Offset in Pixeln vom oberen linken Rand des Ursprungs dar. Die logischen Koordinaten sind die Offsets, die sich ergeben würden, wenn die Pixel selbst skaliert würden.  
  
 Angenommen, Sie entwerfen ein Dialogfeld mit einer Schaltfläche an den Koordinaten (100, 48). Wenn dieses Dialogfeld auf dem Standard-96 dpi angezeigt wird, befindet sich die Schaltfläche bei physikalischen Koordinaten von (100, 48). Bei 120 dpi befindet er sich bei physikalischen Koordinaten von (125, 60). Aber die logischen Koordinaten sind bei jeder dpi-Einstellung gleich: (100, 48).  
  
 Logische Koordinaten sind wichtig, da sie das Verhalten des Betriebssystems und der Anwendungen unabhängig von der dpi-Einstellung konsistent machen. <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> gibt z. B. normalerweise die logischen Koordinaten zurück. Wenn Sie den Cursor über ein Element in einem Dialogfeld bewegen, werden die gleichen Koordinaten unabhängig von der dpi-Einstellung zurückgegeben. Wenn Sie ein Steuerelement bei (100, 100) zeichnen, wird es auf diese logischen Koordinaten gezeichnet und nimmt die gleiche relative Position bei jeder dpi-Einstellung ein.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>
## <a name="scaling-in-ui-automation-clients"></a>Skalierung in Benutzeroberflächenautomatisierungs-Clients  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API verwendet keine logischen Koordinaten. Die folgenden Methoden und Eigenschaften geben entweder physische Koordinaten zurück oder verwenden sie als Parameter.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 Standardmäßig kann eine Benutzeroberflächenautomatisierungsclientanwendung, die in einer Nicht-96-dpi-Umgebung ausgeführt wird, keine korrekten Ergebnisse aus diesen Methoden und Eigenschaften abrufen. Da die Cursorposition z. B. in logischen Koordinaten angegeben wird, kann der Client diese Koordinaten nicht einfach an <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> übergeben, um das Element abzurufen, das sich unter dem Cursor befindet. Darüber hinaus ist die Anwendung nicht in der Lage, Fenster außerhalb seines Clientbereichs ordnungsgemäß zu platzieren.  
  
 Die Lösung besteht aus zwei Teilen.  
  
1. Machen Sie zunächst die Clientanwendung dpi-aware. Rufen Sie dazu beim Start `SetProcessDPIAware` die Win32-Funktion auf. Die folgende Deklaration stellt diese Funktion in verwaltetem Code zur Verfügung.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Diese Funktion macht den gesamten Prozess dpi-bewusst, was bedeutet, dass alle Fenster, die zum Prozess gehören, nicht skaliert werden. Im [Highlighter-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)befinden sich z. B. die vier Fenster, aus denen das Hervorhebungsrechteck besteht, an den physischen Koordinaten, die von der BENUTZERoberflächenautomatisierung abgerufen werden, nicht an den logischen Koordinaten. Wenn das Beispiel nicht dpi-aware wäre, würde die Hervorhebung an den logischen Koordinaten auf dem Desktop gezeichnet werden, was zu einer falschen Platzierung in einer Nicht-96-dpi-Umgebung führen würde.  
  
2. Um Cursorkoordinaten zu erhalten, rufen `GetPhysicalCursorPos`Sie die Win32-Funktion auf. Im folgenden Beispiel wird das Deklarieren und Verwenden dieser Funktion veranschaulicht.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> Verwenden Sie nicht <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Das Verhalten dieser Eigenschaft außerhalb der Clientfenster in einer skalierten Umgebung ist nicht definiert.  
  
 Wenn Ihre Anwendung eine direkte prozessübergreifende Kommunikation mit nicht dpi-basierten Anwendungen durchführt, können Sie mithilfe `PhysicalToLogicalPoint` `LogicalToPhysicalPoint`der Win32-Funktionen und zwischen logischen und physischen Koordinaten konvertieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
