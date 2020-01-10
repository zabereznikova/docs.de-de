---
title: Übersicht über die Technologieregionen
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 0b6ad222737f992da3074770fb5a2bff17860c00
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740288"
---
# <a name="technology-regions-overview"></a>Übersicht über die Technologieregionen
Wenn mehrere Präsentationstechnologien in einer Anwendung verwendet werden, wie z.B. WPF, Win32 oder DirectX, müssen diese die Renderingbereiche in einem gemeinsamen Fenster auf der obersten Ebene gemeinsam verwenden. In diesem Thema werden die Probleme beschrieben, welche die Präsentation und Eingabe für Ihre WPF-Interoperationsanwendung beeinflussen können.  
  
## <a name="regions"></a>Bereiche  
 In einem obersten Fenster können Sie sich jedes HWND, das eine der Technologien einer Interoperationsanwendung umfasst, so vorstellen, als verfüge es über einen eigenen Bereich (auch als „Airspace“ bezeichnet). Jedes Pixel im Fenster gehört zu genau einem HWND, das den Bereich dieses HWND bildet. (Genau genommen ist mehr als ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereich vorhanden, wenn mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-HWNDs vorhanden sind. Für diese Diskussion wird jedoch davon ausgegangen, dass nur ein HWND vorhanden ist). Der Bereich impliziert, dass alle Ebenen oder anderen Fenster, die versuchen, während der Anwendungslebensdauer oberhalb dieses Pixels ein Rendering durchzuführen, Teil der gleichen Renderebenentechnologie sein müssen. Der Versuch, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Pixel über Win32 zu Rendering, führt zu unerwünschten Ergebnissen und ist durch die Interoperation-APIs so weit wie möglich nicht zulässig.  
  
### <a name="region-examples"></a>Beispiele für Bereiche  
 Die folgende Abbildung zeigt eine Anwendung, die Win32, DirectX und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]mischt. Jede Technologie verwendet einen eigenen, nicht überlappenden Satz von Pixeln, und es gibt keine Probleme mit dem Bereich.  
  
 ![Ein Beispiel für eine Anwendung, die Win32, DirectX und WPF vermischt.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Nehmen wir an, diese Anwendung verwendet die Position des Mauszeigers, um eine Animation zu erstellen, die versucht, in einem dieser drei Bereiche ein Rendering durchzuführen. Unabhängig davon, welche Technologie für die Animation selbst verantwortlich ist, würde diese Technologie den Bereich der beiden anderen verletzen. Die folgende Abbildung zeigt einen Versuch, einen WPF-Kreis in einem Win32-Bereich zu rendern.  
  
 ![Es wurde versucht, einen WPF-Kreis über einen Win32-Bereich zu erzeugen.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Auch der Versuch, Transparenz/Alphablending zwischen unterschiedlichen Technologien zu verwenden, stellt eine Verletzung dar.  In der folgenden Abbildung verletzt das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Feld die Win32-und DirectX-Regionen. Da Pixel in diesem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Feld halbtransparent sind, müssten Sie sowohl durch DirectX als auch durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in Besitz sein, was nicht möglich ist.  Dies ist eine weitere Verletzung und kann daher nicht erstellt werden.  
  
 ![Das Diagramm zeigt ein WPF-Feld, das die Win32-und DirectX-Regionen verletzt.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 In den drei vorhergehenden Beispielen wurden rechteckige Bereiche verwendet, andere Formen sind jedoch auch möglich.  Ein Bereich kann z.B. ein Loch aufweisen. In der folgenden Abbildung wird ein Win32-Bereich mit einem rechteckigen Loch dargestellt. Hierbei handelt es sich um die kombinierte Größe der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-und DirectX-Regionen.  
  
 ![Diagramm, das einen Win32-Bereich mit einem rechteckigen Loch zeigt.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Regionen können auch vollständig nicht rechteckig sein, oder jede Form, die durch eine Win32-HRGN (Region) beschreibbar ist.  
  
 ![Diagramm, das einen nicht rechteckigen Bereich anzeigt.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Transparenz und Fenster der obersten Ebene  
 Der Fenster-Manager in Windows verarbeitet nur Win32-HWNDs. Daher ist jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> ein HWND. Der <xref:System.Windows.Window> HWND muss die allgemeinen Regeln für jedes beliebige HWND einhalten. Innerhalb dieses HWND kann [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Code die gesamten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs unterstützen. Allerdings müssen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für Interaktionen mit anderen HWNDs auf dem Desktop die Win32-Verarbeitungs-und Renderingregeln einhalten.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt nicht rechteckige Fenster mithilfe von Win32-APIs – HRGNs für nicht rechteckige Fenster und überlappende Fenster für ein pro-Pixel-Alpha.  
  
 Konstante Alpha-Schlüssel und Farbhintergründe werden nicht unterstützt.  Überlappende Win32-Fenster Funktionen variieren je nach Plattform.  
  
 Überlappende Fenster können dazu führen, dass das gesamte Fenster transparent (semitransparent) wird, indem ein auf jedes Pixel im Fenster anzuwendender Alphawert festgelegt wird.  (Win32 unterstützt pro Pixel Alpha, aber dies ist in praktischen Programmen sehr schwer zu verwenden, da Sie in diesem Modus jedes untergeordnete HWND zeichnen müssen, einschließlich Dialogfeldern und Dropdown Listen).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt HRGNs; für diese Funktionalität gibt es jedoch keine verwalteten APIs. Sie können den Platt Form Aufruf und den <xref:System.Windows.Interop.HwndSource> verwenden, um die relevanten Win32-APIs aufzurufen. Weitere Informationen finden Sie unter [Aufrufen nativer Funktionen aus verwaltetem Code](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] überlappende Fenster haben auf verschiedenen Betriebssystemen verschiedene Funktionen. Dies liegt daran, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DirectX zum Rendern verwendet, und überlappende Fenster speziell für GDI-Rendering, nicht für DirectX-Rendering entworfen wurden.  
  
- WPF unterstützt hardwarebeschleunigte überlappende Fenster.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt keine Transparenz-Hintergrundfarben, da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht das Rendering der genaue Farbe, die Sie angefordert haben, nicht garantieren kann, insbesondere wenn das Rendering hardwarebeschleunigt ist.  
  
## <a name="see-also"></a>Siehe auch

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hosten von Win32-Inhalt in WPF](hosting-win32-content-in-wpf.md)
