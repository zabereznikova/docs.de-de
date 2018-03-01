---
title: Interaktion zwischen WPF und Direct3D9
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: abfdeb4dbf72d0173b020e201f85a30b57cfb3e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interaktion zwischen WPF und Direct3D9
Sie können Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung einschließen. Dieses Thema beschreibt, wie Direct3D9-Inhalt zu erstellen, sodass sie effizient mit WPF zusammenwirkt.  
  
> [!NOTE]
>  Wenn Direct3D9-Inhalt in WPF verwenden zu können, müssen Sie auch an Leistung überlegen. Weitere Informationen dazu, wie Sie die Leistung zu optimieren, finden Sie unter [Überlegungen zur Leistung für WPF-Interoperabilität und Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Anzeigepuffer  
 Die <xref:System.Windows.Interop.D3DImage> -Klasse verwaltet zwei Anzeigepuffer, die aufgerufen werden der *Hintergrundpuffer* und *front Puffer*. Der Hintergrundpuffer ist die Direct3D9-Oberfläche. Änderungen an den Hintergrundpuffer werden auf den Front-Puffer vorwärts kopiert, beim Aufrufen der <xref:System.Windows.Interop.D3DImage.Unlock%2A> Methode.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen den Hintergrundpuffer und Front-Puffers.  
  
 ![D3DImage-Anzeigepuffer](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Erstellen von Direct3D9-Geräts  
 Um Direct3D9 Inhalt rendern, müssen Sie ein Gerät Direct3D9 erstellen. Es gibt zwei Direct3D9-Objekte, die Sie verwenden können, erstellen Sie ein Gerät `IDirect3D9` und `IDirect3D9Ex`. Verwenden Sie zum Erstellen dieser Objekte `IDirect3DDevice9` und `IDirect3DDevice9Ex` Geräte bzw.  
  
 Erstellen Sie ein Gerät, indem eine der folgenden Methoden aufrufen.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 Unter Windows Vista oder höher verwenden die `Direct3DCreate9Ex` Methode mit einer Anzeige, die Verwendung von Windows angezeigt Driver Model (WDDM) konfiguriert ist. Verwenden der `Direct3DCreate9` Methode auf eine andere Plattform.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Verfügbarkeit der Direct3DCreate9Ex-Methode  
 Die Datei d3d9.dll bietet die `Direct3DCreate9Ex` Methode nur unter Windows Vista oder höheren Betriebssystem. Wenn Sie direkt über die Funktion unter Windows XP verknüpfen, wird die Anwendung geladen. Um zu bestimmen, ob die `Direct3DCreate9Ex` Methode unterstützt wird, laden Sie die DLL aus, und suchen Sie nach der Proc-Adresse. Der folgende Code zeigt, wie Sie testen die `Direct3DCreate9Ex` Methode. Ein vollständiges Codebeispiel finden Sie unter [Exemplarische Vorgehensweise: Erstellen von Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>HWND-Erstellung  
 Erstellen ein Gerät erfordert einen HWND. Im Allgemeinen erstellen Sie eine dummy-HWND für Direct3D9 verwenden. Im folgenden Codebeispiel wird veranschaulicht, wie eine dummy-HWND zu erstellen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Vorhandene Parameter  
 Erstellen ein Gerät erfordert außerdem eine `D3DPRESENT_PARAMETERS` -Struktur, aber nur einige Parameter sind wichtig. Diese Parameter werden ausgewählt, um die Speicherverwendung zu minimieren.  
  
 Legen Sie die `BackBufferHeight` und `BackBufferWidth` Felder auf 1. Wenn sie auf 0 festlegen bewirkt, dass sie auf die Dimensionen des HWND festgelegt werden.  
  
 Immer Festlegen der `D3DCREATE_MULTITHREADED` und `D3DCREATE_FPU_PRESERVE` Flags festlegen, um zu verhindern, dass Beschädigung des Speichers von Direct3D9 und um zu verhindern, dass Direct3D9 FPU-Einstellungen ändern.  
  
 Der folgende Code zeigt, wie zum Initialisieren der `D3DPRESENT_PARAMETERS` Struktur.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Erstellen das Renderziel Hintergrundpuffer  
 Anzeige von Direct3D9-Inhalt in ein <xref:System.Windows.Interop.D3DImage>, Sie erstellen eine Direct3D9-Oberfläche, und weisen Sie diese durch Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode.  
  
### <a name="verifying-adapter-support"></a>Überprüfen Sie die Unterstützung für Adapter  
 Vor dem Erstellen einer Oberfläche an, stellen Sie sicher, dass alle Adapter die-Oberfläche Eigenschaften unterstützen, die Sie benötigen. Auch wenn Sie nur einen Adapter rendern, kann das WPF-Fenster auf alle Adapter im System angezeigt. Sie sollten immer Direct3D9 Code schreiben, der mit mehreren Konfigurationen behandelt, und überprüfen Sie alle Adapter unterstützt werden, da die Oberfläche zwischen den verfügbaren Adapter WPF verschoben werden kann.  
  
 Im folgenden Codebeispiel wird veranschaulicht, überprüfen Sie alle Adapter auf dem System Direct3D9 unterstützen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Erstellen der Oberfläche  
 Vor dem Erstellen einer Oberfläche an, stellen Sie sicher, dass die Gerätefunktionen gute Leistung auf dem Ziel-Betriebssystem unterstützt. Weitere Informationen finden Sie unter [Überlegungen zur Leistung für WPF-Interoperabilität und Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Wenn Sie die Gerätefunktionen überprüft haben, können Sie die Oberfläche erstellen. Im folgenden Codebeispiel wird veranschaulicht, wie das Renderziel erstellt.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 Unter Windows Vista und späteren Betriebssystemen, die für die Verwendung der WDDM konfiguriert sind, können Sie eine Textur der Render-Ziel erstellen und übergeben Sie die Oberfläche der Ebene 0, die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode. Dieser Ansatz wird unter Windows XP nicht empfohlen, da Sie eine sperrbare Zieltextur erstellen können und die Leistung reduziert werden wird.  
  
## <a name="handling-device-state"></a>Behandeln von Gerätestatus "  
 Die <xref:System.Windows.Interop.D3DImage> -Klasse verwaltet zwei Anzeigepuffer, die aufgerufen werden der *Hintergrundpuffer* und *front Puffer*. Der Hintergrundpuffer ist die Direct3D-Oberfläche.  Änderungen an den Hintergrundpuffer werden auf den Front-Puffer vorwärts kopiert, beim Aufrufen der <xref:System.Windows.Interop.D3DImage.Unlock%2A> -Methode, in denen es auf die Hardware angezeigt wird. In einigen Fällen wird der Front-Puffer nicht verfügbar. Diese mangelnde Verfügbarkeit kann durch Bildschirm sperren, Vollbild-exklusive Direct3D-Anwendungen, Benutzer wechseln oder andere Systemaktivitäten verursacht werden. In diesem Fall wird die WPF-Anwendung benachrichtigt, durch Behandeln der <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis.  Wie Ihre Anwendung auf den Front-Puffer als nicht verfügbar reagiert, hängt davon ab, ob WPF aktiviert ist, auf Elemente des Softwarerendering zurückgreifen. Die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode verfügt über eine Überladung, die einen Parameter, der angibt akzeptiert, ob WPF Softwarerendering zurückgreift.  
  
 Beim Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> überladen, oder rufen Sie die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> -Überladung mit der `enableSoftwareFallback` Parameter festgelegt wird, um `false`, das Renderingsystem frei seinen Verweis auf den Hintergrundpuffer aus, wenn der Front-Puffer verfügbar ist mehr und keine Daten ist angezeigt. Wenn der Front-Puffer wieder verfügbar ist, löst das Renderingsystem die <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis, um die WPF-Anwendung zu benachrichtigen.  Können, erstellen Sie einen Ereignishandler für das <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis Rendering erneut mit einer gültigen Direct3D-Oberfläche neu starten. Um Rendering neu zu starten, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Beim Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> -Überladung mit der `enableSoftwareFallback` Parametersatz auf `true`, das Renderingsystem behält seinen Verweis auf den Hintergrundpuffer aus, wenn der Front-Puffer ausfällt, daher keine Notwendigkeit zum Aufrufen besteht <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> beim im Vordergrund Puffer steht erneut zur Verfügung.  
  
 Wenn die Elemente des Softwarerendering aktiviert ist, möglicherweise gibt es Situationen, in dem das Gerät des Benutzers nicht mehr verfügbar ist, aber das Renderingsystem behält einen Verweis auf die Direct3D-Oberfläche. Um zu überprüfen, ob ein Direct3D9-Gerät nicht verfügbar ist, rufen Sie die `TestCooperativeLevel` Methode. Einen Aufruf der Direct3D9Ex Geräte Überprüfen der `CheckDeviceState` -Methode, da die `TestCooperativeLevel` Methode ist veraltet und immer erfolgreich zurückgegeben. Wenn das Gerät des Benutzers nicht mehr verfügbar ist, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> unter der WPF Verweis auf den Hintergrundpuffer freigeben.  Aufrufen, wenn Sie Ihr Gerät zurücksetzen müssen, <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> mit der `backBuffer` Parametersatz auf `null`, und rufen Sie anschließend <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> erneut mit `backBuffer` legen Sie auf eine gültige Direct3D-Oberfläche.  
  
 Rufen Sie die `Reset` Methode, um ein ungültiges Gerät keine Wiederherstellung nur, wenn Sie die Unterstützung für mehrere Adapter implementieren. Andernfalls alle Direct3D9 Schnittstellen freigeben und vollständig neu erstellen. Wenn das Adapterlayout geändert wurde, werden die Direct3D9-Objekte, die vor der Änderung erstellt nicht aktualisiert.  
  
## <a name="handling-resizing"></a>Behandlung von Größenänderung  
 Wenn eine <xref:System.Windows.Interop.D3DImage> wird angezeigt, mit einer Auflösung als die systemeigene Größe, wird er gemäß der aktuellen skaliert <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, außer dass <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> für ersetzt <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Wenn Sie eine höhere Genauigkeit erforderlich ist, müssen Sie ein neues erstellen Oberfläche, wenn der Container die <xref:System.Windows.Interop.D3DImage> ändert die Größe.  
  
 Es gibt drei Möglichkeiten zum Ändern der Größe zu behandeln.  
  
-   Das Layoutsystem beteiligt, und erstellen Sie eine neue Oberfläche aus, wenn die Größe ändert. Zu viele Flächen kann nicht erstellt werden, da aufgebraucht sind oder video Arbeitsspeicher fragmentieren kann.  
  
-   Warten Sie, bis eine Resize-Ereignis für einen festen Zeitraum zum Erstellen der neuen Oberfläche stattgefunden hat.  
  
-   Erstellen einer <xref:System.Windows.Threading.DispatcherTimer> überprüft die Containerdimensionen mehrere Male pro Sekunde.  
  
## <a name="multi-monitor-optimization"></a>Optimierung mit mehreren Monitoren  
 Deutlich geringere Leistung kann dazu führen, wenn das Renderingsystem verschiebt eine <xref:System.Windows.Interop.D3DImage> auf einen anderen Bildschirm.  
  
 WDDM, solange die Monitore, auf dem gleichen video sind Karte verwenden `Direct3DCreate9Ex`, es ist keine Verringerung der Leistung. Wenn die Monitore auf separaten Grafikkarten befinden, wird die Leistung beeinträchtigt. Unter Windows XP ist die Leistung immer reduziert.  
  
 Wenn die <xref:System.Windows.Interop.D3DImage> verschiebt auf einen anderen Bildschirm können Sie eine neue Oberfläche erstellen, auf dem entsprechenden Adapter so gute Leistung wiederherstellen.  
  
 Um Leistungseinbußen zu vermeiden, Schreiben Sie Code speziell für den Fall mit mehreren Monitoren. Die folgende Liste zeigt eine Möglichkeit zum Schreiben von Code mit mehreren Monitoren.  
  
1.  Suchen Sie einen Punkt von der <xref:System.Windows.Interop.D3DImage> im Bildschirmbereich mit der `Visual.ProjectToScreen` Methode.  
  
2.  Verwenden der `MonitorFromPoint` GDI-Methode, um den Bildschirm zu suchen, die den Punkt angezeigt wird.  
  
3.  Verwenden der `IDirect3D9::GetAdapterMonitor` Methode zum Suchen von welcher Adapters Direct3D9 des Monitors befindet sich auf.  
  
4.  Wenn der Adapter nicht die Netzwerkkarte mit der Hintergrundpuffer identisch ist, erstellen Sie einen neuen Hintergrundpuffer auf den neuen Monitor, und weisen sie Sie der <xref:System.Windows.Interop.D3DImage> Hintergrundpuffer.  
  
> [!NOTE]
>  Wenn die <xref:System.Windows.Interop.D3DImage> umspannt Monitore, Leistung werden langsam, außer bei WDDM und `IDirect3D9Ex` für denselben Adapter. Es gibt keine Möglichkeit zum Verbessern der Leistung in dieser Situation.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie beim Suchen des aktuellen Monitors.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aktualisieren Sie den Monitor bei der <xref:System.Windows.Interop.D3DImage> Größe oder Position Änderungen des Containers oder das Update des Monitors mithilfe einer `DispatcherTimer` , die nur wenige Male pro Sekunde aktualisiert.  
  
## <a name="wpf-software-rendering"></a>WPF-Elemente des Softwarerendering  
 WPF wird synchron auf den UI-Thread in der Software in den folgenden Situationen gerendert.  
  
-   Drucken  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Wenn eine der folgenden Situationen auftritt, das Renderingsystem Ruft den <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> Methode, um den Puffer für die Hardware, Software kopieren. Die Standardimplementierung Ruft die `GetRenderTargetData` Methode mit der Entwurfsoberfläche. Da dieser Aufruf außerhalb des Musters Sperren/Entsperren auftritt, kann er fehlschlagen. In diesem Fall die `CopyBackBuffer` -Methode zurückkehrt `null` und kein Bild angezeigt wird.  
  
 Sie überschreiben können die <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> -Methode, die basisimplementierung aufrufen und wenn zurückgegeben `null`, können Sie einen Platzhalter zurückgeben <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 Sie können auch Ihre eigenen Elemente des Softwarerendering statt die basisimplementierung aufrufen implementieren.  
  
> [!NOTE]
>  Wenn WPF vollständig in der Software, Rendern von ist <xref:System.Windows.Interop.D3DImage> wird nicht angezeigt werden, da WPF keinen Front-Puffer.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.D3DImage>  
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
