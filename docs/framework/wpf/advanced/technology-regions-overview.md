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
ms.openlocfilehash: 4f1489065a70065700d2f8ceb974e66ecceeebd0
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133816"
---
# <a name="technology-regions-overview"></a>Übersicht über die Technologieregionen
Wenn mehrere Präsentationstechnologien in einer Anwendung verwendet werden, wie z.B. WPF, Win32 oder DirectX, müssen diese die Renderingbereiche in einem gemeinsamen Fenster auf der obersten Ebene gemeinsam verwenden. In diesem Thema werden die Probleme beschrieben, welche die Präsentation und Eingabe für Ihre WPF-Interoperationsanwendung beeinflussen können.  
  
## <a name="regions"></a>Bereiche  
 In einem obersten Fenster können Sie sich jedes HWND, das eine der Technologien einer Interoperationsanwendung umfasst, so vorstellen, als verfüge es über einen eigenen Bereich (auch als „Airspace“ bezeichnet). Jedes Pixel im Fenster gehört zu genau einem HWND, das den Bereich dieses HWND bildet. (Genau genommen ist mehr als ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereich vorhanden, wenn mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-HWNDs vorhanden sind. Für diese Diskussion wird jedoch davon ausgegangen, dass nur ein HWND vorhanden ist). Der Bereich impliziert, dass alle Ebenen oder anderen Fenster, die versuchen, während der Anwendungslebensdauer oberhalb dieses Pixels ein Rendering durchzuführen, Teil der gleichen Renderebenentechnologie sein müssen. Der Versuch, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Pixel zu Rendering, führt zu unerwünschten Ergebnissen und ist durch die Interoperation-APIs so weit wie möglich nicht zulässig.  
  
### <a name="region-examples"></a>Beispiele für Bereiche  
 Die folgende Abbildung zeigt eine Anwendung, die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], DirectX und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]kombiniert. Jede Technologie verwendet einen eigenen, nicht überlappenden Satz von Pixeln, und es gibt keine Probleme mit dem Bereich.  
  
 ![Ein Beispiel für eine Anwendung, die Win32, DirectX und WPF vermischt.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Nehmen wir an, diese Anwendung verwendet die Position des Mauszeigers, um eine Animation zu erstellen, die versucht, in einem dieser drei Bereiche ein Rendering durchzuführen. Unabhängig davon, welche Technologie für die Animation selbst verantwortlich ist, würde diese Technologie den Bereich der beiden anderen verletzen. Die folgende Abbildung zeigt einen Versuch, einen WPF-Kreis in einem Win32-Bereich zu rendern.  
  
 ![Es wurde versucht, einen WPF-Kreis über einen Win32-Bereich zu erzeugen.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Auch der Versuch, Transparenz/Alphablending zwischen unterschiedlichen Technologien zu verwenden, stellt eine Verletzung dar.  In der folgenden Abbildung verstößt das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Feld gegen die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] DirectX-Bereiche und. Da Pixel in diesem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Feld halbtransparent sind, müssten Sie sowohl durch DirectX als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]durch eine gemeinsame, was nicht möglich ist.  Dies ist eine weitere Verletzung und kann daher nicht erstellt werden.  
  
 ![Das Diagramm zeigt ein WPF-Feld, das die Win32-und DirectX-Regionen verletzt.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 In den drei vorhergehenden Beispielen wurden rechteckige Bereiche verwendet, andere Formen sind jedoch auch möglich.  Ein Bereich kann z.B. ein Loch aufweisen. In der folgenden Abbildung wird [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ein Bereich mit einem rechteckigen Loch dargestellt. Hierbei handelt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es sich um die kombinierte Größe der-und DirectX-Regionen.  
  
 ![Diagramm, das einen Win32-Bereich mit einem rechteckigen Loch zeigt.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Bereiche müssen nicht rechteckig sein, und können jede Form aufweisen, die von einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-HRGN (Bereich) definiert werden kann.  
  
 ![Diagramm, das einen nicht rechteckigen Bereich anzeigt.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Transparenz und Fenster der obersten Ebene  
 Der Fenster-Manager in Windows verarbeitet tatsächlich nur [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-HWNDs. Daher handelt es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sich bei jedem <xref:System.Windows.Window> um ein HWND. Das <xref:System.Windows.Window> HWND muss die allgemeinen Regeln für jedes HWND einhalten. Innerhalb dieses HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann Code alle allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] APIs unterstützen. Bei Interaktionen mit anderen HWNDs auf dem Desktop muss [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jedoch die Verarbeitungs- und Renderingregeln von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] beachten.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt nicht rechteckige Fenster mithilfe [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] von APIs – HRGNs für nicht rechteckige Fenster und überlappende Fenster für ein pro-Pixel-Alpha.  
  
 Konstante Alpha-Schlüssel und Farbhintergründe werden nicht unterstützt.  Die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Funktionen für überlappende Fenster variieren je nach Plattform.  
  
 Überlappende Fenster können dazu führen, dass das gesamte Fenster transparent (semitransparent) wird, indem ein auf jedes Pixel im Fenster anzuwendender Alphawert festgelegt wird.  ([!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] unterstützt Alphablending pro Pixel, dessen Verwendung in praktischen Programmen allerdings sehr schwierig ist, da Sie in diesem Modus jedes untergeordnete HWND selbst zeichnen müssen, einschließlich der Dialogfelder und Dropdownmenüs).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt HRGNs; für diese Funktionalität gibt es jedoch keine verwalteten APIs. Sie können den Platt Form Aufruf <xref:System.Windows.Interop.HwndSource> und zum Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relevanten APIs verwenden. Weitere Informationen finden Sie unter [Aufrufen nativer Funktionen aus verwaltetem Code](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] überlappende Fenster haben auf verschiedenen Betriebssystemen verschiedene Funktionen. Dies liegt daran [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , dass DirectX zum Rendern verwendet und überlappende Fenster primär für GDI-Rendering, nicht für DirectX-Rendering entwickelt wurden.  
  
- WPF unterstützt hardwarebeschleunigte überlappende Fenster.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt keine Transparenz-Hintergrundfarben, da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht das Rendering der genaue Farbe, die Sie angefordert haben, nicht garantieren kann, insbesondere wenn das Rendering hardwarebeschleunigt ist.  
  
## <a name="see-also"></a>Siehe auch

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Hosting einer WPF-Uhr in Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hosten von Win32-Inhalt in WPF](hosting-win32-content-in-wpf.md)
