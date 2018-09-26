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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 4fe6a0c39388e72807043e9e1ccd2deb59afb656
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47202506"
---
# <a name="ui-automation-and-screen-scaling"></a>Benutzeroberflächenautomatisierung und Bildschirmskalierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] ermöglicht es Benutzern, die [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)] -Einstellung so zu ändern, dass die meisten [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente auf dem Bildschirm größer erscheinen. Obwohl dieses Feature in [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)]bereits seit längerem verfügbar ist, musste die Skalierung in früheren Versionen von Anwendungen implementiert werden. In [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)]führt der Desktopfenster-Manager standardmäßig die Skalierung für alle Anwendungen aus, die ihre eigene Skalierung nicht übernehmen. Benutzeroberflächenautomatisierungs-Clientanwendungen müssen dieses Feature berücksichtigen.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Skalierung in Windows Vista  
 Der [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Standardeinstellung ist 96, d. h. 96 Pixel belegen eine Breite oder Höhe eines angenommenen Zolls. Das genaue Maß für ein „Zoll“ ist abhängig von der Größe und der physischen Auflösung des Monitors. Auf einem Monitor mit einer Breite von 12 Zoll bei einer horizontalen Auflösung von 1280 Pixel erstreckt sich eine horizontale Linie von 96 Pixeln beispielsweise über etwas 9/10 eines Zolls.  
  
 Das Ändern der [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Einstellung ist nicht dasselbe wie das Ändern der Auflösung. Mit der [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Skalierung bleibt die Anzahl der physischen Pixel auf dem Bildschirm unverändert. Die Skalierung wird jedoch auf die Größe und Position der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente angewendet. Diese Skalierung kann vom Desktopfenster-Manager (DWM) für den Desktop und für Anwendungen automatisch durchgeführt werden , die nicht ausdrücklich danach verlangen, nicht skaliert zu werden.  
  
 Wenn der Benutzer den Skalierungsfaktor auf 120 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]festlegt, wird ein vertikales oder horizontales Zoll auf dem Bildschirm um 25 Prozent vergrößert. Alle Dimensionen werden entsprechend skaliert. Der Offset eines Anwendungsfensters vom oberen und linken Rand des Bildschirms wird um 25 Prozent erhöht. Wenn die Anwendungsskalierung aktiviert ist und die Anwendung nicht mit [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatibel ist, wird das Fenster zusammen mit den Offsets und Größen aller darin enthaltenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente im selben Verhältnis vergrößert.  
  
> [!NOTE]
>  Standardmäßig führt der Desktopfenster-Manager keine Skalierung für nicht mit[!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatible Anwendungen durch, wenn der Benutzer für [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] den Wert 120 festlegt. Die Skalierung wird jedoch ausgeführt, wenn für [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] ein benutzerdefinierter Wert von 144 oder höher festgelegt wird. Das Standardverhalten kann vom Benutzer jedoch außer Kraft gesetzt werden.  
  
 Die Bildschirmskalierung stellt an Anwendungen neue Herausforderungen, die sich in irgendeiner Weise mit Bildschirmkoordinaten befassen. Der Bildschirm enthält jetzt zwei Koordinatensysteme: ein physisches und ein logisches. Die physischen Koordinaten eines Punkts stellen den tatsächlichen Offset in Pixeln vom oberen linken Rand des Ursprungs dar. Die logischen Koordinaten sind die Offsets, die sich ergeben würden, wenn die Pixel selbst skaliert würden.  
  
 Angenommen, Sie entwerfen ein Dialogfeld mit einer Schaltfläche an den Koordinaten (100, 48). Wenn dieses Dialogfeld mit den standardmäßigen 96 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]angezeigt wird, dann befindet sich die Schaltfläche an den physischen Koordinaten (100, 48). Bei 120 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]befindet sie sich an den physischen Koordinaten (125, 60). Aber die logischen Koordinaten sind bei jeder [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Einstellung dieselben: (100, 48).  
  
 Logische Koordinaten sind wichtig, da sie für Betriebssystem und Anwendungen unabhängig von der [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Einstellung für ein konsistentes Verhalten sorgen. Z. B. <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> normalerweise die logischen Koordinaten zurück. Wenn Sie den Cursor über ein Element in einem Dialogfeld bewegen, werden unabhängig von der [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Einstellung dieselben Koordinaten zurückgegeben. Wenn Sie ein Steuerelement an den Koordinaten (100, 100) darstellen, wird es an diesen logischen Koordinaten angezeigt und belegt bei einer beliebigen [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Einstellung dieselbe relative Position.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Skalierung in Benutzeroberflächenautomatisierungs-Clients  
 Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [!INCLUDE[TLA#tla_api](../../../includes/tlasharptla-api-md.md)] does not use logical coordinates. Die folgenden Methoden und Eigenschaften geben entweder physische Koordinaten zurück oder verwenden sie als Parameter.  
  
-   <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
-   <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 Standardmäßig ist eine Benutzeroberflächenautomatisierungs-Clientanwendung, die in einer Nicht-96- [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Umgebung ausgeführt wird, nicht in der Lage, von diesen Methoden und Eigenschaften die richtigen Ergebnisse zu erhalten. Da die Cursorposition z. B. in logischen Koordinaten angegeben wird, kann der Client diese Koordinaten nicht einfach an <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> übergeben, um das Element abzurufen, das sich unter dem Cursor befindet. Darüber hinaus ist die Anwendung nicht in der Lage, Fenster außerhalb seines Clientbereichs ordnungsgemäß zu platzieren.  
  
 Die Lösung besteht aus zwei Teilen.  
  
1.  Zunächst sorgen Sie dafür, dass die Clientanwendung mit [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatibel ist. Rufen Sie dazu die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `SetProcessDPIAware` beim Start auf. Die folgende Deklaration stellt diese Funktion in verwaltetem Code zur Verfügung.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Diese Funktion sorgt dafür, dass der gesamte Prozess mit [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatibel ist, d. h. alle zum Prozess gehörenden Fenster werden nicht skaliert. In der [Highlighter Sample](https://msdn.microsoft.com/library/19ba4577-753e-4efd-92cc-c02ee67c1b69), befinden sich beispielsweise die vier Fenster, die das hervorgehobene Rechteck bilden an den physischen Koordinaten, die aus abgerufen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], nicht an den logischen Koordinaten. Wenn das Beispiel nicht mit [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatibel wäre, würde die Hervorhebung an den logischen Koordinaten auf dem Desktop dargestellt werden, was zu einer falschen Platzierung in einer Nicht-96- [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] -Umgebung führen würde.  
  
2.  Rufen Sie die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktion `GetPhysicalCursorPos`auf, um Cursorkoordinaten abzurufen. Im folgenden Beispiel wird das Deklarieren und Verwenden dieser Funktion veranschaulicht.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
>  Verwenden Sie nicht <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. Das Verhalten dieser Eigenschaft außerhalb der Clientfenster in einer skalierten Umgebung ist nicht definiert.  
  
 Wenn Ihre Anwendung eine direkte prozessübergreifende Kommunikation mit nicht mit [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]-Werten kompatiblen Anwendungen unterhält, müssen Sie mithilfe der [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Funktionen `PhysicalToLogicalPoint` und `LogicalToPhysicalPoint`möglicherweise zwischen logischen und physischen Koordinaten konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Highlighter Sample](https://msdn.microsoft.com/library/19ba4577-753e-4efd-92cc-c02ee67c1b69)
