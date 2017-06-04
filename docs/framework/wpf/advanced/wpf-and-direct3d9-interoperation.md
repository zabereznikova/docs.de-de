---
title: "Interaktion zwischen WPF und Direct3D9 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [WPF-Interoperabilität], Erstellen von Direct3D9-Inhalten"
  - "WPF, Erstellen von Direct3D9-Inhalten"
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Interaktion zwischen WPF und Direct3D9
Sie können Direct3D9\-Inhalt in eine WPF\-Anwendung \(Windows Presentation Foundation\) einschließen.  In diesem Thema wird beschrieben, wie Direct3D9\-Inhalt so erstellt wird, dass er effizient mit WPF zusammenwirkt.  
  
> [!NOTE]
>  Wenn Sie Direct3D9\-Inhalt in WPF verwenden, müssen Sie auch über die Leistung nachdenken.  Weitere Informationen zur Leistungsoptimierung finden Sie unter [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## Anzeigen von Puffern  
 Die <xref:System.Windows.Interop.D3DImage>\-Klasse verwaltet zwei Anzeigepuffer, die als *Hintergrundpuffer* und *Frontpuffer* bezeichnet werden.  Der Hintergrundpuffer ist die Direct3D\-Oberfläche.  Änderungen am Hintergrundpuffer werden beim Aufrufen der <xref:System.Windows.Interop.D3DImage.Unlock%2A>\-Methode weiter in den Frontpuffer kopiert.  
  
 In der folgenden Abbildung wird die Beziehung zwischen dem Hintergrundpuffer und dem Frontpuffer dargestellt.  
  
 ![D3Dimage&#45;Anzeigepuffer](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage\_buffers")  
  
## Direct3D9\-Geräteerstellung  
 Um Direct3D9\-Inhalt zu rendern, müssen Sie ein Direct3D9\-Gerät erstellen.  Es gibt zwei Direct3D9\-Objekte, die Sie verwenden können, um ein Gerät zu erstellen, `IDirect3D9` und `IDirect3D9Ex`.  Verwenden Sie diese Objekte, um `IDirect3DDevice9`\- bzw. `IDirect3DDevice9Ex`\-Geräte zu erstellen.  
  
 Erstellen Sie ein Gerät, indem Sie eine der folgenden Methoden aufrufen.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 Unter Windows Vista oder neuerem Betriebssystem verwenden Sie die `Direct3DCreate9Ex`\-Methode mit einer Anzeige, die so konfiguriert ist, dass das Windows\-Anzeigetreibermodell \(WDDM\) zu verwenden.  Verwenden Sie die `Direct3DCreate9`\-Methode auf einer beliebigen anderen Plattform.  
  
### Verfügbarkeit der Direct3DCreate9Ex\-Methode  
 Das d3d9.dll hat die `Direct3DCreate9Ex`\-Methode nur unter Windows Vista oder neuerem Betriebssystem.  Wenn Sie die Funktion direkt unter Windows XP verknüpfen, wird die Anwendung nicht geladen.  Um zu ermitteln, ob die `Direct3DCreate9Ex`\-Methode unterstützt wird, laden Sie die DLL und suchen Sie nach der Prozeduradresse.  Im folgenden Code wird dargestellt, wie für die `Direct3DCreate9Ex`\-Methode getestet wird.  Ein vollständiges Codebeispiel finden Sie unter [Exemplarische Vorgehensweise: Erstellen von Direct3D9\-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### HWND\-Erstellung  
 Für die Erstellung eines Geräts ist ein HWND erforderlich.  Im Allgemeinen erstellen Sie einen Dummy\-HWND, der von Direct3D9 verwendet werden kann.  Im folgenden Codebeispiel wird das Erstellen eines Dummy\-HWND veranschaulicht.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### Vorhandene Parameter  
 Für die Erstellung eines Geräts ist zwar auch eine `D3DPRESENT_PARAMETERS`\-Struktur erforderlich, aber es sind nur einige Parameter wichtig.  Diese Parameter werden ausgewählt, um die Speicherbeanspruchung zu minimieren.  
  
 Legen Sie die Felder `BackBufferHeight` und `BackBufferWidth` auf 1 fest.  Wenn Sie diese Felder auf 0 festlegen, werden sie auf die Dimensionen des HWND festgelegt.  
  
 Legen Sie die Flags `D3DCREATE_MULTITHREADED` und `D3DCREATE_FPU_PRESERVE` fest, damit kein von Direct3D9 verwendeter Speicher beschädigt wird und damit Direct3D9 keine FPU\-Einstellungen ändert.  
  
 Im folgenden Code wird dargestellt, wie die `D3DPRESENT_PARAMETERS`\-Struktur initialisiert wird.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## Erstellen des Hintergrundpuffer\-Renderingziels  
 Wenn Sie Direct3D9\-Inhalt in <xref:System.Windows.Interop.D3DImage> anzeigen möchten, erstellen Sie eine Direct3D9\-Oberfläche und weisen Sie diese zu, indem Sie die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>\-Methode aufrufen.  
  
### Überprüfen der Adapterunterstützung  
 Bevor Sie eine Oberfläche erstellen, überprüfen Sie, dass alle Adapter die erforderlichen Oberflächeneigenschaften unterstützen.  Selbst wenn Sie nur zu einem Adapter rendern, kann das WPF\-Fenster für jeden beliebigen Adapter im System angezeigt werden.  Sie sollten immer Direct3D9\-Code schreiben, der Multiadapter\-Konfigurationen verarbeitet, und sie sollten überprüfen, ob alle Adapter unterstützt werden, da WPF die Oberfläche zwischen den verfügbaren Adaptern verschieben kann.  
  
 Im folgenden Codebeispiel wird dargestellt, wie überprüft wird, ob alle Adapter auf dem System Direct3D9 unterstützen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### Erstellen der Oberfläche  
 Überprüfen Sie vor dem Erstellen einer Oberfläche, ob die Gerätefunktionen unter dem Zielbetriebssystem eine gute Leistung unterstützen.  Weitere Informationen hierzu finden Sie unter [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Wenn Sie die Gerätefunktionen überprüft haben, können Sie die Oberfläche erstellen.  Im folgenden Codebeispiel wird dargestellt, wie das Renderingziel erstellt wird.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### WDDM  
 Unter Windows Vista und höheren Betriebssystemen die konfiguriert werden, um das WDDM zu verwenden, können Sie eine Renderingzieltextur erstellen und die Oberfläche der Ebene 0 zur <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>\-Methode übergeben.  Diese Methode wird unter Windows XP nicht empfohlen, da Sie keine sperrbare Zieltextur erstellen können und die Leistung reduziert wird.  
  
## Behandlung des Gerätezustands  
 Die <xref:System.Windows.Interop.D3DImage>\-Klasse verwaltet zwei Anzeigepuffer, die als *Hintergrundpuffer* und *Frontpuffer* bezeichnet werden.  Der Hintergrundpuffer ist die Direct3D\-Oberfläche.  Änderungen am Hintergrundpuffer werden den Frontpuffer kopiert, wenn Sie die <xref:System.Windows.Interop.D3DImage.Unlock%2A>\-Methode aufgerufen werden, in der sie auf der Hardware angezeigt wird.  Gelegentlich wird der Frontpuffer nicht verfügbar.  Diese mangelnde Verfügbarkeit kann durch Sperren des Bildschirms, exklusive Direct3D\-Anwendungen im Vollbildmodus, Benutzerwechsel oder andere Systemaktivitäten verursacht werden.  Wenn dies auftritt, wird die WPF\-Anwendung benachrichtigt, indem das <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>\-Ereignis behandelt.  Wie die Anwendung auf den Frontpuffer reagiert, der nicht verfügbar ist, hängt davon ab, ob WPF aktiviert ist, auf das Softwarerendering zurückzugreifen.  Die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>\-Methode hat eine Überladung, die einen Parameter, der angibt, ob WPF als Softwarerendering fällt.  
  
 Wenn Sie die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> Überladung aufrufen oder die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> überladung mit dem `enableSoftwareFallback`\-Parameter aufrufen, der zu `false` festgelegt ist, gibt das Renderingsystem den Verweis auf den Hintergrundpuffer frei, wenn der Frontpuffer nicht verfügbar ist und keine angezeigt wird.  Wenn der Frontpuffer wieder verfügbar ist, löst das Renderingsystem <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> das Ereignis aus, um die WPF\-Anwendung zu benachrichtigen.  Sie können einen Ereignishandler erstellen, damit das <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>\-Ereignis mit einer gültigen Direct3D\-Oberfläche erneut rendern neu gestartet.  Um Rendering neu zu starten, müssen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> aufrufen.  
  
 Wenn Sie die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> überladung mit dem `enableSoftwareFallback`\-Parameter aufrufen, der zu `true` festgelegt wird, behält das Renderingsystem den Verweis auf den Hintergrundpuffer, wenn der Frontpuffer nicht verfügbar ist, sodass keine, <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> aufzurufen bei, wenn der Frontpuffer wieder verfügbar ist.  
  
 Wenn Softwarerendering aktiviert ist, gibt jedoch Situationen, in denen das Gerät des Benutzers nicht verfügbar ist, und das Renderingsystem einen Verweis auf die Direct3D\-Oberfläche beibehält.  Um sicherzustellen dass ein Direct3D9\-Gerät nicht verfügbar ist, rufen Sie die `TestCooperativeLevel`\-Methode auf.  Um ein Direct3D9Ex\-Geräte zu überprüfen, rufen Sie die `CheckDeviceState`\-Methode auf, da die `TestCooperativeLevel`\-Methode veraltet ist und immer erfolgreich zurückgegeben wird.  Wenn das Benutzergerät nicht verfügbar geworden ist, rufen <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>, um Verweises WPF dem Hintergrundpuffer freizugeben.  Wenn Sie das Gerät zurücksetzen müssen, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> mit dem `backBuffer`\-Parameter auf, der zu `null` festgelegt ist, und rufen Sie dann <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> erneut mit `backBuffer` auf, das einer gültigen Direct3D\-Oberfläche festgelegt ist.  
  
 Rufen Sie die `Reset`\-Methode für die Wiederherstellung von einem ungültigen Gerät nur dann auf, wenn Sie die Multiadapter\-Unterstützung implementieren.  Geben Sie andernfalls alle Direct3D9\-Oberflächen frei und erstellen Sie diese völlig neu.  Wenn sich das Adapterlayout geändert hat, werden die vor der Änderung erstellten Direct3D9\-Objekte nicht aktualisiert.  
  
## Behandlung der Größenanpassung  
 Wenn <xref:System.Windows.Interop.D3DImage> an einer anderen Auflösung als der systemeigenen Größe angezeigt wird, wird sie entsprechend aktuellen <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> skaliert, außer dass <xref:System.Windows.Media.Effects.SamplingMode> wird für <xref:System.Windows.Media.BitmapScalingMode> ersetzt.  
  
 Wenn Sie eine höhere Originaltreue benötigen, müssen Sie eine neue Oberfläche erstellen, sobald sich die Containergröße von <xref:System.Windows.Interop.D3DImage> ändert.  
  
 Es gibt drei Methoden für die Größenanpassung.  
  
-   Nehmen Sie am Layoutsystem teil und erstellen Sie eine neue Oberfläche, wenn sich die Größe ändert.  Erstellen Sie nicht zu viele Oberflächen, da Sie möglicherweise Videospeicher erschöpfen oder fragmentieren.  
  
-   Warten Sie, bis für einen längeren Zeitraum kein Größenanpassungsereignis stattgefunden hat, um die neue Oberfläche zu erstellen.  
  
-   Erstellen Sie einen <xref:System.Windows.Threading.DispatcherTimer>, der die Containerdimensionen mehrmals pro Sekunde überprüft.  
  
## Optimierung mit mehreren Bildschirmen  
 Die erheblich reduzierte Leistung kann sich ergeben, wenn das Renderingsystem ein <xref:System.Windows.Interop.D3DImage> auf einen anderen Bildschirm verschiebt.  
  
 Solange sich die Bildschirme unter WDDM auf derselben Videokarte befinden und Sie `Direct3DCreate9Ex` verwenden, ist die Leistung nicht reduziert.  Wenn sich die Bildschirme auf separaten Videokarten befinden, ist die Leistung reduziert.  Unter Windows XP ist die Leistung immer reduziert.  
  
 Wenn das <xref:System.Windows.Interop.D3DImage> auf einen anderen Bildschirm verschoben wird, können Sie auf dem entsprechenden Adapter eine neue Oberfläche für die Wiederherstellung einer guten Leistung erstellen.  
  
 Um Leistungseinbußen zu vermeiden, schreiben Sie Code ausdrücklich für den Fall von mehreren Bildschirmen.  In der folgenden Liste wird eine Möglichkeit dargestellt, Code für mehrere Bildschirme zu schreiben.  
  
1.  Suchen Sie mit der `Visual.ProjectToScreen`\-Methode einen Punkt von <xref:System.Windows.Interop.D3DImage> im Bildschirmkoordinatensystem.  
  
2.  Verwenden Sie die `MonitorFromPoint`\-GDI\-Methode, um den Bildschirm zu suchen, der den Punkt anzeigt.  
  
3.  Verwenden Sie die `IDirect3D9::GetAdapterMonitor`\-Methode, um zu ermitteln, auf welchem Direct3D9\-Adapter sich der Bildschirm befindet.  
  
4.  Falls es sich bei dem Adapter nicht um den Adapter mit dem Hintergrundpuffer handelt, erstellen Sie für den neuen Bildschirm einen neuen Hintergrundpuffer und weisen Sie ihn dem <xref:System.Windows.Interop.D3DImage>\-Hintergrundpuffer zu.  
  
> [!NOTE]
>  Falls <xref:System.Windows.Interop.D3DImage> mehrere Monitore umspannt, führt dies zu einer langsamen Leistung, außer, wenn sich WDDM und `IDirect3D9Ex` auf demselben Adapter befinden.  Es gibt keine Möglichkeit, die Leistung in dieser Situation zu verbessern.  
  
 Im folgenden Codebeispiel wird dargestellt, wie Sie den aktuellen Bildschirm suchen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aktualisieren Sie den Bildschirm, wenn sich die Containergröße oder Position von <xref:System.Windows.Interop.D3DImage> ändert oder aktualisieren Sie den Bildschirm mit einem `DispatcherTimer`, der mehrere Aktualisierungen pro Sekunde durchführt.  
  
## WPF\-Softwarerendering  
 WPF führt in den folgenden Situationen ein synchrones Rendering für den UI\-Thread in Software durch.  
  
-   Drucken  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Wenn eine der Situationen auftritt, ruft das Renderingsystem die <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>\-Methode zum Kopieren des Hardwarepuffers in die Software auf.  Die Standardimplementierung ruft die `GetRenderTargetData`\-Methode mit der Oberfläche auf.  Da dieser Aufruf außerhalb des Lock\/Unlock\-Musters \(Sperren\/Entsperren\) auftritt, schlägt er möglicherweise fehl.  In diesem Fall gibt die `CopyBackBuffer`\-Methode `null` zurück, und es wird kein Bild angezeigt.  
  
 Sie können die <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>\-Methode überschreiben, die Basisimplementierung aufrufen und falls `null` zurückgegeben wird, einen Platzhalter <xref:System.Windows.Media.Imaging.BitmapSource> zurückgeben.  
  
 Sie können auch ein eigenes Softwarerendering implementieren, statt die Basisimplementierung aufzurufen.  
  
> [!NOTE]
>  Falls WPF vollständig in der Software rendert, wird <xref:System.Windows.Interop.D3DImage> nicht angezeigt, da WPF nicht über einen Frontpuffer verfügt.  
  
## Siehe auch  
 <xref:System.Windows.Interop.D3DImage>   
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Exemplarische Vorgehensweise: Erstellen von Direct3D9\-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten von Direct3D9\-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)