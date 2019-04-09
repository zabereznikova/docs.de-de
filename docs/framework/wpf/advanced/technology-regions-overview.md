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
ms.openlocfilehash: 911ba1474677f26a773ff63e958ba0ceedbefd0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100976"
---
# <a name="technology-regions-overview"></a>Übersicht über die Technologieregionen
Wenn mehrere Präsentationstechnologien in einer Anwendung verwendet werden, wie z.B. WPF, Win32 oder DirectX, müssen diese die Renderingbereiche in einem gemeinsamen Fenster auf der obersten Ebene gemeinsam verwenden. In diesem Thema werden die Probleme beschrieben, welche die Präsentation und Eingabe für Ihre WPF-Interoperationsanwendung beeinflussen können.  
  
## <a name="regions"></a>Bereiche  
 In einem obersten Fenster können Sie sich jedes HWND, das eine der Technologien einer Interoperationsanwendung umfasst, so vorstellen, als verfüge es über einen eigenen Bereich (auch als „Airspace“ bezeichnet). Jedes Pixel im Fenster gehört zu genau einem HWND, das den Bereich dieses HWND bildet. (Genau genommen ist mehr als ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereich vorhanden, wenn mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-HWNDs vorhanden sind. Für diese Diskussion wird jedoch davon ausgegangen, dass nur ein HWND vorhanden ist). Der Bereich impliziert, dass alle Ebenen oder anderen Fenster, die versuchen, während der Anwendungslebensdauer oberhalb dieses Pixels ein Rendering durchzuführen, Teil der gleichen Renderebenentechnologie sein müssen. Der Versuch, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Pixel über [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] zu rendern, führt zu unerwünschten Ergebnissen und ist während der Interoperation der [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]s so weit wie möglich zu vermeiden.  
  
### <a name="region-examples"></a>Beispiele für Bereiche  
 Die folgende Abbildung zeigt eine Anwendung, in der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kombiniert werden. Jede Technologie verwendet einen eigenen, nicht überlappenden Satz von Pixeln, und es gibt keine Probleme mit dem Bereich.  
  
 ![Ein Fenster ohne Airspace-Probleme](./media/migrationinteroparchitectarticle01.png "MigrationInteropArchitectArticle01")  
  
 Nehmen wir an, diese Anwendung verwendet die Position des Mauszeigers, um eine Animation zu erstellen, die versucht, in einem dieser drei Bereiche ein Rendering durchzuführen. Unabhängig davon, welche Technologie für die Animation selbst verantwortlich ist, würde diese Technologie den Bereich der beiden anderen verletzen. Die folgende Abbildung zeigt einen Versuch, einen WPF-Kreis in einem Win32-Bereich zu rendern.  
  
 ![Interop-Diagramm](./media/migrationinteroparchitectarticle02.png "MigrationInteropArchitectArticle02")  
  
 Auch der Versuch, Transparenz/Alphablending zwischen unterschiedlichen Technologien zu verwenden, stellt eine Verletzung dar.  In der folgenden Abbildung verletzt das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Feld die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]- und [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Bereiche. Da die Pixel in diesem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Feld semitransparent sind, müssten sie sowohl zu [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehören, was nicht möglich ist.  Dies ist eine weitere Verletzung und kann daher nicht erstellt werden.  
  
 ![Interop-Diagramm](./media/migrationinteroparchitectarticle03.png "MigrationInteropArchitectArticle03")  
  
 In den drei vorhergehenden Beispielen wurden rechteckige Bereiche verwendet, andere Formen sind jedoch auch möglich.  Ein Bereich kann z.B. ein Loch aufweisen. Die folgende Abbildung zeigt einen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Bereich mit einem rechteckigen Loch, dessen Größe dem kombinierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- und [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Bereich entspricht.  
  
 ![Interop-Diagramm](./media/migrationinteroparchitectarticle04.png "MigrationInteropArchitectArticle04")  
  
 Bereiche müssen nicht rechteckig sein, und können jede Form aufweisen, die von einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-HRGN (Bereich) definiert werden kann.  
  
 ![Interop-Diagramm](./media/migrationinteroparchitectarticle05.png "MigrationInteropArchitectArticle05")  
  
## <a name="transparency-and-top-level-windows"></a>Transparenz und Fenster der obersten Ebene  
 Der Fenster-Manager in Windows verarbeitet tatsächlich nur [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-HWNDs. Aus diesem Grund jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> ein HWND. Die <xref:System.Windows.Window> -HWND muss die allgemeinen Richtlinien für alle HWNDS erfüllen. Innerhalb dieses HWND kann von dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code alles durchgeführt werden, was von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] unterstützt wird. Bei Interaktionen mit anderen HWNDs auf dem Desktop muss [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jedoch die Verarbeitungs- und Renderingregeln von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] beachten.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt von nicht rechteckigen Windows mithilfe von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]– HRGNs für nicht rechteckige Fenster und überlappende Fenster für eine Alphablending pro Pixel.  
  
 Konstante Alpha-Schlüssel und Farbhintergründe werden nicht unterstützt.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Funktionen für überlappende Fenster variieren je nach Plattform.  
  
 Überlappende Fenster können dazu führen, dass das gesamte Fenster transparent (semitransparent) wird, indem ein auf jedes Pixel im Fenster anzuwendender Alphawert festgelegt wird.  ([!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] unterstützt Alphablending pro Pixel, dessen Verwendung in praktischen Programmen allerdings sehr schwierig ist, da Sie in diesem Modus jedes untergeordnete HWND selbst zeichnen müssen, einschließlich der Dialogfelder und Dropdownmenüs).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt HRGNs ist. Es gibt jedoch keine verwalteten [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] für diese Funktionalität. Sie können die Plattform aufrufen und <xref:System.Windows.Interop.HwndSource> aufrufen, die relevanten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Weitere Informationen finden Sie unter [Aufrufen nativer Funktionen aus verwaltetem Code](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] überlappende Fenster haben verschiedene Funktionen auf verschiedenen Betriebssystemen. Das liegt darin, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zum Rendern [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] verwendet, und überlappende Fenster in erster Linie für das [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]-Rendering und nicht für das [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Rendering konzipiert sind.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt hardwarebeschleunigte überlappende Fenster unter [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] und höher. Hardwarebeschleunigte überlappende Fenster unter [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)] erfordern die Unterstützung von [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)], sodass die Funktionen von der [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)]-Version auf diesem Computer abhängig sind.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt keine Transparenz, da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann nicht garantieren, der Rendering der genaue Farbe Sie angefordert haben, insbesondere dann, wenn Rendering hardwarebeschleunigt ist.  
  
-   Wenn die Anwendung auf [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)] ausgeführt wird, führen überlappende Fenster über [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Oberflächen während des Renderings durch die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]-Anwendung zu Flimmern.  (Die eigentliche Rendering-Sequenz ist wie folgt: [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] blendet das überlappende Fenster aus, anschließend zeichnet [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], und dann zeigt [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] das überlappende Fenster erneut an).  Überlappende Fenster ohne [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besitzen diese Einschränkung ebenfalls.  
  
## <a name="see-also"></a>Siehe auch

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hosten von Win32-Inhalt in WPF](hosting-win32-content-in-wpf.md)
