---
title: "Renderingebenen f&#252;r Grafiken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Renderingebenen für Grafiken"
  - "Grafiken, Leistung"
  - "Grafiken, Renderingebenen"
  - "Rendern von Grafiken"
  - "Renderingebenen"
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
caps.latest.revision: 44
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 43
---
# Renderingebenen f&#252;r Grafiken
Eine Renderingebene definiert den Umfang der Funktionen und Leistung der Grafikhardware für ein Gerät, auf dem eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ausgeführt wird.  
  
   
  
<a name="graphics_hardware"></a>   
## Grafikhardware  
 Folgende Features der Grafikhardware wirken sich besonders stark auf die Renderingebenen aus:  
  
-   **Video\-RAM**: Der Umfang des Video\-Arbeitsspeichers der Grafikhardware bestimmt die Größe und Anzahl der Puffer, die für die Zusammensetzung von Grafiken verwendet werden können.  
  
-   **Pixelshader**: Ein Pixelshader ist eine Grafikverarbeitungsfunktion, die Effekte auf der Basis einzelner Pixel berechnet.  Je nach Auflösung der angezeigten Grafiken müssen möglicherweise für jeden angezeigten Frame mehrere Millionen Pixel verarbeitet werden.  
  
-   **Vertexshader**: Ein Vertexshader ist eine Grafikverarbeitungsfunktion, die mathematische Operationen für die Vertexdaten des Objekts ausführt.  
  
-   **Unterstützung von Mehrfachtexturen**: Hierbei handelt es sich um die Fähigkeit, während eines Blendingvorgangs mehrere unterschiedliche Texturen auf ein 3D\-Grafikobjekt anzuwenden.  Der Grad der Unterstützung von Mehrfachtexturen hängt von der Anzahl der Mehrfachtextureinheiten in der Grafikhardware ab.  
  
<a name="rendering_tier_definitions"></a>   
## Definitionen von Renderingebenen  
 Die Features der Grafikhardware bestimmen die Renderingfähigkeit einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung.  Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-System definiert drei Renderingebenen:  
  
-   **Renderingebene 0 \(null\)** Keine Grafikhardwarebeschleunigung.  Alle Grafikfeatures verwenden die Softwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt in einer niedrigeren Version als 9.0 vor.  
  
-   **Renderingebene 1** Einige Grafikfeatures verwenden die Grafikhardwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt mindestens in Version 9.0 vor.  
  
-   **Renderingebene 2** Die meisten Grafikfeatures verwenden die Grafikhardwarebeschleunigung.  Die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Versionsebene liegt mindestens in Version 9.0 vor.  
  
 Die <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=fullName>\-Eigenschaft ermöglicht es Ihnen, die Renderingebene zur Anwendungslaufzeit abzurufen.  Anhand der Renderingebene bestimmen Sie, ob das Gerät bestimmte hardwarebeschleunigte Grafikfunktionen unterstützt.  Je nach der vom Gerät unterstützten Renderingebene kann die Anwendung zur Laufzeit dann verschiedenen Codepfaden folgen.  
  
### Renderingebene 0 \(null\)  
 Der Wert 0 \(null\) für die Renderingebene bedeutet, dass auf diesem Gerät für die Anwendung keine Grafikhardwarebeschleunigung verfügbar ist.  Auf dieser Ebene sollten Sie davon ausgehen, dass alle Grafiken von Software ohne Hardwarebeschleunigung gerendert werden.  Die Funktionen dieser Ebene entsprechen einer [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Version, die niedriger als 9.0 ist.  
  
### Renderingebene 1 und Renderingebene 2  
  
> [!NOTE]
>  Ab .NET Framework 4 wurde die Renderingebene 1 neu definiert, um nur Grafikhardware einzuschließen, die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 9.0 oder höher unterstützt.  Grafikhardware, die [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 7 oder 8 unterstützt, ist nun als Renderingebene 0 definiert.  
  
 Ein Renderingebenenwert von 1 oder 2 gibt an, dass die meisten Grafikfunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Hardwarebeschleunigung verwenden, wenn die erforderlichen Systemressourcen verfügbar und nicht überlastet sind.  Dies entspricht einer [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Version von 9.0 oder höher.  
  
 In der folgenden Tabelle sind die Unterschiede bezüglich der Grafikhardwareanforderungen für Renderingebene 1 und Renderingebene 2 aufgeführt:  
  
|Feature|Ebene 1|Ebene 2|  
|-------------|-------------|-------------|  
|[!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Version|Muss mindestens 9.0 sein.|Muss mindestens 9.0 sein.|  
|Video\-RAM|Muss größer oder gleich 60 MB sein.|Muss mindestens 120 MB betragen.|  
|Pixel\-Shader|Die Versionsebene muss mindestens 2.0 sein.|Die Versionsebene muss mindestens 2.0 sein.|  
|Vertex\-Shader|Keine Anforderung.|Die Versionsebene muss mindestens 2.0 sein.|  
|Mehrfachtextureinheiten|Keine Anforderung.|Die Anzahl der Einheiten muss mindestens 4 betragen.|  
  
 Die folgenden Funktionen sind für Renderingebene 1 und Renderingebene 2 hardwarebeschleunigt:  
  
|Feature|Hinweise|  
|-------------|--------------|  
|2D\-Rendering|Die meisten 2D\-Renderingfunktionen werden unterstützt.|  
|3D\-Rasterung|Die meisten 3D\-Rasterungsfunktionen werden unterstützt.|  
|Anisotropische 3D\-Filterung|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] versucht, 3D\-Inhalt mithilfe der anisotropischen Filterung zu rendern.  Die anisotropische Filterung dient der verbesserten Bildqualität von Texturen auf Oberflächen, die weit von der Kamera entfernt sind und in einem steilen Winkel zur Kamera stehen.|  
|MIP\-Zuordnung im 3D\-Bereich|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] versucht, 3D\-Inhalt mithilfe der MIP\-Zuordnung zu rendern. Die MIP\-Zuordnung verbessert die Qualität des Rendering von Texturen, wenn eine Textur in <xref:System.Windows.Controls.Viewport3D> ein kleineres Sichtfeld belegt.|  
|Radiale Farbverläufe|Vermeiden Sie die Verwendung von <xref:System.Windows.Media.RadialGradientBrush> für große Objekte, obwohl dies unterstützt wird.|  
|3D\-Beleuchtungsberechnungen|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führt eine vertexspezifische Beleuchtung durch, d. h. eine Lichtintensität muss bei jedem Vertex für jedes Material, das auf ein Gitter angewendet wird, berechnet werden.|  
|Rendern von Text|Beim Subpixel\-Rendering von Schriftarten werden verfügbare Pixel\-Shader der Grafikhardware verwendet.|  
  
 Die folgenden Funktionen sind nur für Renderingebene 2 hardwarebeschleunigt:  
  
|Feature|Hinweise|  
|-------------|--------------|  
|3D\-Antialiasing|3D\-Antialiasing wird nur auf Betriebssystemen unterstützt, die das Windows\-Anzeigetreibermodell \(Windows Display Driver Model, WDDM\) unterstützen, z. B. [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] und [!INCLUDE[win7](../../../../includes/win7-md.md)].|  
  
 Die folgenden Funktionen sind **nicht** hardwarebeschleunigt:  
  
|Feature|Hinweise|  
|-------------|--------------|  
|Ausgegebene Inhalte|Alle ausgegebenen Inhalte werden mithilfe der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Softwarepipeline gerendert.|  
|Gerasterte Inhalte, die <xref:System.Windows.Media.Imaging.RenderTargetBitmap> verwenden.|Alle Inhalte, die mithilfe der <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A>\-Methode von <xref:System.Windows.Media.Imaging.RenderTargetBitmap> gerendert werden.|  
|Gekachelte Inhalte, die <xref:System.Windows.Media.TileBrush> verwenden|Gekachelte Inhalte, bei denen die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft von <xref:System.Windows.Media.TileBrush> auf <xref:System.Windows.Media.TileMode> festgelegt ist.|  
|Oberflächen, die die maximale Texturgröße der Grafikhardware überschreiten|Gängige Grafikhardware unterstützt meist Oberflächen mit einer Größe von 2048x2048 oder 4096x4096 Pixeln.|  
|Alle Vorgänge, deren Anforderungen an den Video\-RAM den Speicher der Grafikhardware übersteigen|Sie können mithilfe des in der [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md) im Windows SDK enthaltenen Perforator\-Tools anzeigen, wie viel Grafikspeicher eine Anwendung verwendet.|  
|Überlappende Fenster|Mithilfe von überlappenden Fenstern können [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen Inhalte auf dem Bildschirm in einem nicht rechteckigen Fenster rendern.  Bei Betriebssystemen, die das Windows\-Anzeigetreibermodell \(WDDM\) unterstützen \(z. B. [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] und [!INCLUDE[win7](../../../../includes/win7-md.md)]\), sind überlappende Fenster hardwarebeschleunigt.  Unter anderen Betriebssystemen, z. B. [!INCLUDE[winxp](../../../../includes/winxp-md.md)], werden überlappende Fenster durch Software ohne Hardwarebeschleunigung gerendert.<br /><br /> Sie können überlappende Fenster in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aktivieren, indem Sie die folgenden <xref:System.Windows.Window>\-Eigenschaften festlegen:<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> \= <xref:System.Windows.WindowStyle><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> \= `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> \= <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>   
## Weitere Ressourcen  
 Die folgenden Ressourcen können Ihnen helfen, die Leistungsmerkmale der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung zu analysieren.  
  
### Registrierungseinstellungen für das Rendern von Grafiken  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt vier Registrierungseinstellungen zum Steuern des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Rendering bereit:  
  
|Einstellung|Beschreibung|  
|-----------------|------------------|  
|**Option zum Deaktivieren der Hardwarebeschleunigung**|Gibt an, ob die Hardwarebeschleunigung aktiviert werden soll.|  
|**Maximaler Wert für Multisampling**|Gibt den Grad des Multisampling für das Antialiasing von [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Inhalten an.|  
|**Einstellung für das erforderliche Videotreiberdatum**|Gibt an, ob das System die Hardwarebeschleunigung für Treiber deaktiviert, die vor November 2004 veröffentlicht wurden.|  
|**Option zum Verwenden der Referenz\-Rasterisierungsfunktion**|Gibt an, ob [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Referenz\-Rasterisierungsfunktion verwenden soll.|  
  
 Auf diese Einstellungen kann mit jedem externen Konfigurationsdienstprogramm zugegriffen werden, das auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Registrierungseinstellungen verweisen kann.  Diese Einstellungen lassen sich auch erstellen oder ändern, indem mithilfe des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Registrierungs\-Editors direkt auf die Werte zugegriffen wird.  Weitere Informationen finden Sie unter [Registrierungseinstellungen für das Rendern von Grafiken](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md).  
  
### WPF\-Leistungsprofilerstellungstools  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Suite von Tools zum Erstellen von Leistungsprofilen bereit, mit denen Sie das Laufzeitverhalten einer Anwendung analysieren und die Typen der anwendbaren Leistungsoptimierungen bestimmen können.  In der folgenden Tabelle werden die Leistungsprofilerstellungstools aufgeführt, die im [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)]\-Tool WPF Performance Suite enthalten sind:  
  
|Tool|Beschreibung|  
|----------|------------------|  
|Perforator|Zum Analysieren des Renderingverhaltens.|  
|Visual Profiler|Zur Profilerstellung der Verwendung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Diensten, z. B. Layout und Ereignisbehandlung, durch Elemente in der visuellen Struktur.|  
  
 Die WPF Performance Suite bietet eine leistungsfähige grafische Ansicht der Leistungsdaten.  Weitere Informationen zu Tools zum Erstellen von WPF\-Leistungsprofilen finden Sie unter [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md).  
  
### DirectX\-Diagnosetool  
 Das [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Diagnosetool Dxdiag.exe dient zum Beheben von Problemen im Zusammenhang mit [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  Der Standardinstallationsordner für das [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Diagnosetool ist:  
  
 `~\Windows\System32`  
  
 Beim Ausführen des [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Diagnosetools enthält das Hauptfenster eine Reihe von Registerkarten, mit denen Sie Informationen im Zusammenhang mit [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] anzeigen und einer Diagnose unterziehen können.  Die Registerkarte **System** z. B. bietet Systeminformationen über den Computer und gibt die auf dem Computer installierte [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Version an.  
  
 ![Bildschirmabbildung: DirectX&#45;Diagnosetool](../../../../docs/framework/wpf/advanced/media/directxdiagnostictool-01.png "DirectXDiagnosticTool\_01")  
 Hauptfenster des DirectX\-Diagnosetools  
  
## Siehe auch  
 <xref:System.Windows.Media.RenderCapability>   
 <xref:System.Windows.Media.RenderOptions>   
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md)   
 [Registrierungseinstellungen für das Rendern von Grafiken](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md)   
 [Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)