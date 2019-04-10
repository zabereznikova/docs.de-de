---
title: Interaktion zwischen WPF und Direct3D9
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 38f5eb36e3e5c055c5a354a67e15cde8049a2967
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307729"
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interaktion zwischen WPF und Direct3D9
Sie können Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung einschließen. In diesem Thema wird beschrieben, wie zum Erstellen von Direct3D9-Inhalt, damit sie effizient mit WPF interagiert wird.  
  
> [!NOTE]
>  Bei Verwendung von Direct3D9-Inhalt in WPF müssen Sie auch über die Leistung nachdenken. Weitere Informationen dazu, wie Sie die Leistung zu optimieren, finden Sie unter [Leistungsüberlegungen hinsichtlich Direct3D9 und WPF-Interoperabilität](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Anzeigen von Puffern  
 Die <xref:System.Windows.Interop.D3DImage> Klasse verwaltet zwei Anzeigepuffer, die aufgerufen werden, die *Hintergrundpuffer* und *Frontpuffer*. Der Hintergrundpuffer ist Ihre Direct3D9-Oberfläche. Änderungen an den Hintergrundpuffer werden in den Frontpuffer vorwärts kopiert, beim Aufrufen der <xref:System.Windows.Interop.D3DImage.Unlock%2A> Methode.  
  
 Die folgende Abbildung zeigt die Beziehung zwischen den Hintergrundpuffer und der Front-Puffer.  
  
 ![D3DImage-Anzeigepuffer](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Erstellen von Direct3D9-Geräts  
 Um Direct3D9 Inhalt rendern, müssen Sie ein Direct3D9-Gerät erstellen. Es gibt zwei Direct3D9-Objekte, die Sie, zum Erstellen eines Geräts verwenden können, `IDirect3D9` und `IDirect3D9Ex`. Verwenden Sie zum Erstellen dieser Objekte `IDirect3DDevice9` und `IDirect3DDevice9Ex` Geräten bzw.  
  
 Erstellen Sie ein Gerät, indem Sie eine der folgenden Methoden aufrufen.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 Auf Windows Vista oder höher verwendet wird, verwenden Sie die `Direct3DCreate9Ex` -Methode mit einer Anzeige ab, die Verwendung der Windows anzeigen Driver Model (WDDM) konfiguriert ist. Verwenden der `Direct3DCreate9` Methode für eine andere Plattform.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Verfügbarkeit der Direct3DCreate9Ex-Methode  
 Die Datei d3d9.dll bietet die `Direct3DCreate9Ex` Methode nur auf Windows Vista oder höher verwendet wird. Wenn Sie direkt über die Funktion unter Windows XP verknüpfen, wird die Anwendung nicht geladen werden. Um zu bestimmen, ob die `Direct3DCreate9Ex` -Methode unterstützt wird, laden Sie die DLL aus, und suchen Sie nach der Prozeduradresse. Der folgende Code zeigt, wie Sie testen die `Direct3DCreate9Ex` Methode. Ein vollständiges Codebeispiel finden Sie unter [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>HWND-Erstellung  
 Erstellen ein Gerät erfordert ein HWND. Im Allgemeinen erstellen Sie eine dummy-HWND für Direct3D9 verwenden. Im folgenden Codebeispiel wird veranschaulicht, einen dummy-HWND zu erstellen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Vorhandene Parameter  
 Erstellen ein Gerät erfordert auch eine `D3DPRESENT_PARAMETERS` -Struktur, aber nur ein paar Parameter wichtig sind. Diese Parameter werden ausgewählt, um den Speicherbedarf zu minimieren.  
  
 Legen Sie die `BackBufferHeight` und `BackBufferWidth` Felder auf 1. Wenn sie auf ' 0 bewirkt, dass sie auf die Dimensionen des HWND festgelegt werden.  
  
 Immer Festlegen der `D3DCREATE_MULTITHREADED` und `D3DCREATE_FPU_PRESERVE` Flags festlegen, um zu verhindern, dass Beschädigung des Speichers von Direct3D9 und zu verhindern, dass Direct3D9 FPU ändern verwendet.  
  
 Der folgende Code zeigt, wie Sie initialisieren den `D3DPRESENT_PARAMETERS` Struktur.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Erstellen das Renderziel Hintergrundpuffer  
 Zum Anzeigen von Direct3D9-Inhalten in einem <xref:System.Windows.Interop.D3DImage>, Sie erstellen eine Direct3D9-Oberfläche, und weisen Sie sie durch Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode.  
  
### <a name="verifying-adapter-support"></a>Überprüfen der Unterstützung für Adapter  
 Vor dem Erstellen einer Oberfläche, stellen Sie sicher, dass alle Adapter die Oberflächen Eigenschaften unterstützen, die Sie benötigen. Auch wenn Sie nur einen Adapter rendern, kann das WPF-Fenster auf alle Adapter im System angezeigt. Schreiben Sie immer Direct3D9-Code, der mit mehreren Adapterkonfigurationen behandelt, und überprüfen Sie alle Adapter unterstützt, da die Oberfläche für die verfügbaren Adapter WPF verschoben werden kann.  
  
 Im folgenden Codebeispiel wird veranschaulicht, überprüfen Sie alle Adapter auf dem System für Direct3D9 unterstützen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Erstellen der Oberfläche  
 Vor dem Erstellen einer Oberfläche, stellen Sie sicher, dass die Gerätefunktionen guten Leistung auf dem Ziel-Betriebssystem unterstützt. Weitere Informationen finden Sie unter [Leistungsüberlegungen hinsichtlich Direct3D9 und WPF-Interoperabilität](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Wenn Sie auf die Funktionen überprüft haben, können Sie die Oberfläche erstellen. Im folgenden Codebeispiel wird veranschaulicht, wie das Renderziel erstellt.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 Auf Windows Vista und späteren Betriebssystemen zur Verfügung, die für die Verwendung der WDDM konfiguriert sind, können Sie erstellen Sie eine Textur der Render-Ziel und übergeben Sie die Oberfläche der Ebene 0, die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode. Dieser Ansatz wird unter Windows XP nicht empfohlen, da eine sperrbare Textur kann nicht erstellt und die Leistung reduziert.  
  
## <a name="handling-device-state"></a>Behandlung von Gerätestatus  
 Die <xref:System.Windows.Interop.D3DImage> Klasse verwaltet zwei Anzeigepuffer, die aufgerufen werden, die *Hintergrundpuffer* und *Frontpuffer*. Der Hintergrundpuffer ist Ihrer Direct3D-Oberfläche.  Änderungen an den Hintergrundpuffer werden in den Frontpuffer vorwärts kopiert, beim Aufrufen der <xref:System.Windows.Interop.D3DImage.Unlock%2A> -Methode, in dem sie auf die Hardware angezeigt wird. In einigen Fällen wird der Front-Puffer nicht verfügbar. Diese mangelnde Verfügbarkeit kann durch Bildschirm sperren, Vollbild-exklusive Direct3D-Anwendungen, wechseln von Benutzern oder anderen Systemaktivitäten, die verursacht werden. In diesem Fall wird die WPF-Anwendung benachrichtigt, durch Behandeln der <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis.  Wie Ihre Anwendung in den Frontpuffer nicht verfügbar reagiert, hängt davon ab, ob WPF aktiviert ist, um auf Softwarerendering zurückzugreifen. Die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Methode verfügt über eine Überladung, die einen Parameter, der angibt annimmt, ob WPF auf Softwarerendering zurückgegriffen.  
  
 Beim Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> überladen, oder rufen Sie die <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> -Überladung mit der `enableSoftwareFallback` Parametersatz zu `false`, das rendernde System gibt seinen Verweis auf den Hintergrundpuffer frei, wenn es sich bei der Front-Puffer mehr verfügbar ist, und "nothing" ist angezeigt. Wenn die Frontpuffer wieder verfügbar ist, löst das Renderingsystem die <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis, um die WPF-Anwendung zu benachrichtigen.  Sie können angeben, erstellen einen Ereignishandler für die <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> Ereignis, um das Rendering erneut mit einer gültigen Direct3D-Oberfläche neu zu starten. Um Rendering neu zu starten, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Beim Aufrufen der <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> -Überladung mit dem `enableSoftwareFallback` Parametersatz zu `true`, das rendernde System behält seinen Verweis auf den Hintergrundpuffer, wird der Front-Puffer nicht verfügbar, daher keine Notwendigkeit zum Aufrufen besteht <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> beim im Vordergrund Puffer ist wieder verfügbar.  
  
 Wenn Softwarerendering aktiviert ist, gibt es möglicherweise Situationen, in dem das Gerät des Benutzers nicht mehr verfügbar ist, aber das rendernde System behält einen Verweis auf die Direct3D-Oberfläche. Um zu überprüfen, ob ein Direct3D9-Gerät nicht verfügbar ist, rufen Sie die `TestCooperativeLevel` Methode. Um einen Aufruf der Direct3D9Ex Geräte überprüfen die `CheckDeviceState` -Methode, da die `TestCooperativeLevel` Methode ist veraltet und immer erfolgreich zurückgegeben. Wenn das Gerät des Benutzers nicht mehr verfügbar ist, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> WPF Verweis auf den Hintergrundpuffer freigibt.  Wenn Sie Ihr Gerät zurücksetzen möchten, rufen Sie <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> mit der `backBuffer` Parametersatz zu `null`, und rufen Sie anschließend <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> mit `backBuffer` legen Sie auf eine gültige Direct3D-Oberfläche.  
  
 Rufen Sie die `Reset` Methode zur Wiederherstellung nach eines ungültigen Geräts nur dann, wenn Sie Unterstützung für mehrere Adapter implementieren. Klicken Sie andernfalls alle Direct3D9-Schnittstellen freigeben, und vollständig neu erstellt werden. Wenn das Adapterlayout geändert wurde, werden Direct3D9-Objekte, die vor der Änderung erstellt nicht aktualisiert werden.  
  
## <a name="handling-resizing"></a>Behandeln von Ändern der Größe  
 Wenn eine <xref:System.Windows.Interop.D3DImage> wird mit einer Auflösung als der systemeigenen Größe, wird sie gemäß der aktuellen skaliert <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, außer dass <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> durch ersetzt, <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Wenn Sie eine höhere Genauigkeit erforderlich ist, müssen Sie ein neues erstellen auftreten, wenn der Container die <xref:System.Windows.Interop.D3DImage> ändert die Größe.  
  
 Es gibt drei mögliche Vorgehensweisen für das Ändern der Größe zu behandeln.  
  
-   Das Layoutsystem teilnehmen Sie, und erstellen Sie eine neue Oberfläche, wenn die Größe ändert. Zu viele Oberflächen, kann nicht erstellt werden, weil Sie möglicherweise erschöpft oder Videospeicher fragment.  
  
-   Warten Sie, bis ein Resize-Ereignis nicht für einen festen Zeitraum zum Erstellen der neuen Oberfläche aufgetreten ist.  
  
-   Erstellen Sie eine <xref:System.Windows.Threading.DispatcherTimer> die überprüft, ob die Abmessungen der Container mehrere Male pro Sekunde.  
  
## <a name="multi-monitor-optimization"></a>Optimierung mit mehreren Bildschirmen  
 Kann zu erheblichen Leistungseinbußen führen, wenn bewegt, der Renderingsystem wird eine <xref:System.Windows.Interop.D3DImage> auf einen anderen Bildschirm.  
  
 WDDM, solange die Monitore auf dem gleichen video-Karte und Sie verwenden `Direct3DCreate9Ex`, es gibt keine Verringerung der Leistung. Wenn die Monitore auf separaten Videokarten sind, wird die Leistung beeinträchtigt. Unter Windows XP wird die Leistung immer reduziert.  
  
 Wenn die <xref:System.Windows.Interop.D3DImage> verschiebt auf einen anderen Bildschirm können Sie eine neue Oberfläche auf den entsprechenden Adapter Wiederherstellung einer guten Leistung erstellen.  
  
 Um die Leistungseinbuße zu vermeiden, Schreiben Sie Code speziell für den Fall von mehreren Bildschirmen. Die folgende Liste zeigt eine Möglichkeit, mehrere Monitore Code zu schreiben.  
  
1. Suchen Sie einen Punkt von der <xref:System.Windows.Interop.D3DImage> in Platz auf dem Bildschirm mit der `Visual.ProjectToScreen` Methode.  
  
2. Verwenden der `MonitorFromPoint` GDI-Methode, um den Monitor zu ermitteln, die den Punkt angezeigt wird.  
  
3. Verwenden der `IDirect3D9::GetAdapterMonitor` Methode zu welcher Direct3D9-Adapter finden Sie den Monitor befindet sich auf.  
  
4. Wenn der Adapter nicht identisch mit den Adapter mit den Hintergrundpuffer ist, erstellen Sie einen neuen Back-Puffer für den neuen Bildschirm, und weisen sie Sie der <xref:System.Windows.Interop.D3DImage> Hintergrundpuffer.  
  
> [!NOTE]
>  Wenn die <xref:System.Windows.Interop.D3DImage> umspannt Monitore, die Leistung ist langsam sein, außer im Fall von WDDM und `IDirect3D9Ex` für denselben Adapter. Es gibt keine Möglichkeit zur Verbesserung der Leistung in dieser Situation.  
  
 Im folgenden Codebeispiel wird veranschaulicht, die den aktuellen Bildschirm zu suchen.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Aktualisieren Sie den Monitor bei der <xref:System.Windows.Interop.D3DImage> des Containers Größe oder Position Änderungen oder Updates der Monitor mit einer `DispatcherTimer` , aktualisiert einige Male pro Sekunde.  
  
## <a name="wpf-software-rendering"></a>Rendern von WPF-Software  
 WPF wird synchron im UI-Thread in der Software in den folgenden Situationen gerendert.  
  
-   Drucken  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Tritt eine der folgenden Situationen auf, der Renderingsystem Ruft die <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> Methode, um den Puffer für die Hardware auf Software zu kopieren. Die Standardimplementierung Ruft die `GetRenderTargetData` -Methode mit Ihrer Oberfläche. Da dieser Aufruf außerhalb des Musters Sperren/Entsperren auftritt, kann es fehlschlagen. In diesem Fall die `CopyBackBuffer` Methodenrückgabe `null` und kein Bild angezeigt wird.  
  
 Können Sie überschreiben die <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> -Methode aufrufen die basisimplementierung wird und gibt `null`, können Sie einen Platzhalter zurückkehren <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 Sie können auch Ihre eigenen Softwarerendering anstelle von Aufrufen der basisimplementierung implementieren.  
  
> [!NOTE]
>  Wenn WPF vollständig in Software, rendert <xref:System.Windows.Interop.D3DImage> wird nicht angezeigt werden, da WPF keinen Frontpuffer verfügt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.D3DImage>
- [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
