---
title: Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 52085579c2a432e7db1ebec096a931e0d51718f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF
Direct3D9 Inhalte können gehostet werden, mithilfe der <xref:System.Windows.Interop.D3DImage> Klasse. Direct3D9-Inhalt hosten, kann die Leistung der Anwendung beeinträchtigen. Dieses Thema beschreibt bewährte Methoden zum Optimieren der Leistung beim Hosten von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung. Diese bewährten Methoden enthalten, wie <xref:System.Windows.Interop.D3DImage> und bewährte Methoden aus, wenn Sie Windows Vista, Windows XP, und es mit mehreren Monitoren wird angezeigt.  
  
> [!NOTE]
>  Codebeispiele, die diese bewährten Methoden zu veranschaulichen, finden Sie unter [WPF und Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Verwenden Sie nur selten D3DImage  
 Direct3D9 Inhalt gehostet wird, einem <xref:System.Windows.Interop.D3DImage> Instanz wird nicht als hoch wie bei einer reinen Direct3D-Anwendung gerendert. Kopieren die Oberfläche und leeren des Befehlspuffers können kostenintensive Vorgänge sein. Als die Anzahl der <xref:System.Windows.Interop.D3DImage> Instanzen zunimmt, weitere leeren tritt auf, und die Leistung wird beeinträchtigt. Daher sollten Sie verwenden <xref:System.Windows.Interop.D3DImage> nur selten.  
  
## <a name="best-practices-on-windows-vista"></a>Bewährte Methoden unter Windows Vista  
 Für optimale Leistung unter Windows Vista mit einer Anzeige, die Verwendung von Windows angezeigt Driver Model (WDDM) konfiguriert ist, erstellen Sie eine Direct3D9-Oberfläche für ein `IDirect3DDevice9Ex` Gerät. Dies ermöglicht die-Oberfläche Freigabe. Muss die Grafikkarte unterstützt die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` und `D3DCAPS2_CANSHARERESOURCE` Treiber Funktionen unter Windows Vista. Alle anderen Einstellungen dazu führen, dass die Oberfläche zu kopierenden über Software, die Leistung erheblich reduziert wird.  
  
> [!NOTE]
>  Wenn Windows Vista eine Anzeige, die verfügt Verwendung der Windows XP anzuzeigen Treiber Modell (XDDM) konfiguriert ist, wird die Oberfläche immer über Software, unabhängig von den Einstellungen kopiert. Mit den richtigen Einstellungen und die Grafikkarte sehen Sie eine bessere Leistung unter Windows Vista bei der Verwendung der WDDM, da-Oberfläche Kopien in Hardware ausgeführt werden.  
  
## <a name="best-practices-on-windows-xp"></a>Bewährte Methoden unter Windows XP  
 Für optimale Leistung unter Windows XP, Windows XP Anzeige Treiber Modell (XDDM) verwendet, erstellen Sie eine sperrbare Oberfläche an, die ordnungsgemäß verhält, wenn die `IDirect3DSurface9::GetDC` -Methode aufgerufen wird. Intern wird die `BitBlt` -Methode überträgt die Fläche auf Geräten in der Hardware. Die `GetDC` -Methode funktioniert bei XRGB-Oberflächen immer. Allerdings funktioniert, wenn der Clientcomputer Windows XP mit SP3 oder SP2 ausgeführt wird und wenn der Client auch den Hotfix für die Funktion überlappende Fenster hat, diese Methode nur für ARGB-Oberflächen. Muss die Grafikkarte unterstützt die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` Treiber-Funktion.  
  
 Eine 16-Bit-desktop Anzeigetiefe kann die Leistung erheblich reduzieren. Ein 32-Bit-Desktop wird empfohlen.  
  
 Wenn Sie für Windows Vista und Windows XP entwickeln, testen Sie die Leistung unter Windows XP. Video Arbeitsspeicher unter Windows XP knapp ist relevant. Darüber hinaus <xref:System.Windows.Interop.D3DImage> unter Windows XP verwendet werden soll, mehr Videospeicher und Bandbreite als Windows Vista WDDM aufgrund einer erforderlichen zusätzlichen Grafikspeicher kopieren. Aus diesem Grund können Sie die Leistung schlimmer unter Windows XP als unter Windows Vista für denselben Grafikhardware sein rechnen.  
  
> [!NOTE]
>  XDDM ist unter Windows XP und Windows Vista verfügbar. WDDM ist jedoch nur unter Windows Vista verfügbar.  
  
## <a name="general-best-practices"></a>Allgemein empfohlene Vorgehensweisen  
 Wenn Sie das Gerät erstellen, verwenden die `D3DCREATE_MULTITHREADED` Erstellungsflag. Dadurch wird die Leistung, aber das WPF-Rendering-System ruft Methoden auf diesem Gerät aus einem anderen Thread. Achten Sie darauf, das Sperre Protokoll ordnungsgemäß befolgen, so, dass keine zwei Threads gleichzeitig auf das Gerät zugreifen.  
  
 Wenn das Rendering in einem WPF verwalteten Thread ausgeführt wird, wird dringend empfohlen, dass Sie das Gerät bei Erstellen der `D3DCREATE_FPU_PRESERVE` Erstellungsflag. Ohne diese Einstellung wird das D3D-Rendering verringert sich die Genauigkeit von WPF mit doppelter Genauigkeit Vorgängen und Rendering-Problemen.  
  
 Kacheln ein <xref:System.Windows.Interop.D3DImage> ist schnell, es sei denn, Sie nebeneinander anordnen und eine Fläche, die nicht pow2 ohne hardwareunterstützung oder Sie nebeneinander anordnen und eine <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> , enthält eine <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Bewährte Methoden für zeigt mit mehreren Monitoren  
 Wenn Sie einen Computer, der über mehrere Monitore verfügt verwenden, sollten Sie die zuvor beschriebenen bewährten Methoden befolgen. Es gibt auch einige zusätzliche Leistungsaspekte für eine Konfiguration mit mehreren Monitoren.  
  
 Bei der Erstellung der Hintergrundpuffer es auf einem bestimmten Gerät und der Adapter erstellt wird, aber WPF front Puffer in den alle Adapter anzeigen. Kopieren zwischen Adapter zum Aktualisieren des Front-Puffers kann sehr teuer sein. Unter Windows Vista, die so konfiguriert ist, dass WDDM mit mehreren Grafikkarten und Verwenden einer `IDirect3DDevice9Ex` Gerät ist die Front-Puffer auf einen anderen Adapter jedoch weiterhin die gleichen Grafikkarte, es gibt keine Leistungseinbußen. Unter Windows XP und der XDDM mit mehreren Grafikkarten besteht jedoch eine erhebliche Leistungseinbußen bei der Front-Puffer mit einem anderen Adapter als dem Hintergrundpuffer angezeigt wird. Weitere Informationen finden Sie unter [WPF und Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Leistung-Zusammenfassung  
 Die folgende Tabelle zeigt die Leistung bei der Aktualisierung Front-Puffer als Funktion des Betriebssystems, Pixelformat und-Oberfläche Lockability. Die Front-Puffer und Hintergrundpuffer wird angenommen, dass für denselben Adapter. Je nach der Konfiguration des Adapters sind Hardwareupdates im Allgemeinen viel schneller als Softwareupdates.  
  
|-Oberfläche Pixelformat|Windows Vista, WDDM und 9Ex|Andere Windows Vista-Konfigurationen|Windows XP SP3 oder SP2 mit hotfix|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (nicht gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT_X8R8G8B8 (sperrbarer)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|**Hardwareupdate**|  
|D3DFMT_A8R8G8B8 (nicht gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT_A8R8G8B8 (sperrbarer)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|Softwareupdate|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.D3DImage>  
 [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
 [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
