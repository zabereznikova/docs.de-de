---
title: Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 1371fa901bebc503a0091f3229a8fd7e6ccc2c86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772852"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF
Sie können die Direct3D9-Inhalt hosten, mit der <xref:System.Windows.Interop.D3DImage> Klasse. Hosten von Direct3D9-Inhalt, kann die Leistung Ihrer Anwendung beeinträchtigen. Dieses Thema beschreibt bewährte Methoden zum Optimieren der Leistung beim Hosten von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung. Diese bewährten Methoden enthalten, wie Sie mit <xref:System.Windows.Interop.D3DImage> und best Practices, wenn Sie Windows Vista, Windows XP verwenden und mit mehreren Monitoren angezeigt.  
  
> [!NOTE]
>  Codebeispiele, die diese bewährten Methoden zu veranschaulichen, finden Sie unter [zwischen WPF und Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Verwenden Sie nur selten D3DImage  
 Direct3D9-Inhalt gehostet wird, einem <xref:System.Windows.Interop.D3DImage> Instanz wird nicht gerendert, so schnell wie in einer reinen Direct3D-Anwendung. Kopieren der Oberfläche und leeren des Befehlspuffers können kostspielige Vorgänge sein. Als die Anzahl der <xref:System.Windows.Interop.D3DImage> Instanzen erhöht, weitere leeren auftritt und die Leistung beeinträchtigt wird. Daher sollten Sie verwenden <xref:System.Windows.Interop.D3DImage> sparsam.  
  
## <a name="best-practices-on-windows-vista"></a>Best Practices für Windows Vista  
 Für eine optimale Leistung unter Windows Vista mit einer Anzeige ab, die Verwendung der Windows anzeigen Driver Model (WDDM) konfiguriert ist, erstellen Sie eine Direct3D9-Oberfläche auf einer `IDirect3DDevice9Ex` Gerät. Dadurch können die Oberfläche freigeben. Muss die Grafikkarte unterstützen die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` und `D3DCAPS2_CANSHARERESOURCE` Treiber Funktionen unter Windows Vista. Alle anderen Einstellungen dazu führen, dass die Oberfläche über Software, die Leistung erheblich reduziert wird, kopiert werden soll.  
  
> [!NOTE]
>  Verfügt Windows Vista eine Anzeige, die Verwendung der Windows XP zeigt Treiber Modell (XDDM) konfiguriert ist, wird die Oberfläche immer über Software, unabhängig von den Einstellungen kopiert werden. Mit den richtigen Einstellungen und die Grafikkarte sehen Sie eine bessere Leistung in Windows Vista bei der Verwendung der WDDM, da Kopien der Oberfläche in der Hardware ausgeführt werden.  
  
## <a name="best-practices-on-windows-xp"></a>Best Practices für Windows XP  
 Für eine optimale Leistung unter Windows XP, dem der Windows XP Display Driver Model (XDDM) verwendet wird, erstellen Sie eine Oberfläche gesperrt werden kann, die ordnungsgemäß verhält. wenn die `IDirect3DSurface9::GetDC` Methode wird aufgerufen. Intern wird die `BitBlt` -Methode überträgt die Oberfläche auf Geräten in der Hardware. Die `GetDC` -Methode funktioniert immer bei XRGB-Oberflächen. Allerdings funktioniert, wenn der Clientcomputer Windows XP mit SP3 oder SP2 ausgeführt wird und wenn der Client auch den Hotfix für das Feature für überlappende Fenster hat, diese Methode nur auf über den ARGB-Oberflächen. Muss die Grafikkarte unterstützen die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` Treiber-Funktion.  
  
 Eine 16-Bit-Desktopanzeigetiefe kann die Leistung erheblich reduziert. Eine 32-Bit-Desktops wird empfohlen.  
  
 Wenn Sie für Windows Vista und Windows XP entwickeln, testen Sie die Leistung unter Windows XP. Videospeicher zur Neige geht unter Windows XP ist ein Problem. Darüber hinaus <xref:System.Windows.Interop.D3DImage> unter Windows XP verwendet wird, mehr Videospeicher und Bandbreite als Windows Vista WDDM aufgrund eines eine Kopie der erforderlichen zusätzlichen Videospeicher. Aus diesem Grund können Sie die Leistung noch schlimmer ist unter Windows XP als unter Windows Vista für die gleiche Videohardware sein erwarten.  
  
> [!NOTE]
>  XDDM ist unter Windows XP und Windows Vista verfügbar. WDDM ist jedoch nur auf Windows Vista verfügbar.  
  
## <a name="general-best-practices"></a>Allgemein empfohlene Vorgehensweisen  
 Wenn Sie das Gerät zu erstellen, verwenden Sie die `D3DCREATE_MULTITHREADED` Flag der Erstellung. Dies verringert die Leistung, aber das WPF-Rendering-System ruft Methoden auf diesem Gerät aus einem anderen Thread. Achten Sie darauf, um das Sperrprotokoll korrekt einhalten, damit, dass keine zwei Threads gleichzeitig auf das Gerät zugreifen.  
  
 Wenn das Rendering in einem WPF verwalteten Thread ausgeführt wird, es wird dringend empfohlen, dass es sich bei der Erstellung des Geräts mit der `D3DCREATE_FPU_PRESERVE` Flag der Erstellung. Ohne diese Einstellung wird das D3D-Rendering verringert sich die Genauigkeit der WPF-Gleitkommazahl mit doppelter Genauigkeit Vorgänge und Rendering-Problemen.  
  
 Unterteilung einer <xref:System.Windows.Interop.D3DImage> ist schnell, es sei denn, Sie ohne Unterstützung für Serverhardware nicht pow2 Oberfläche Kachel oder wenn Sie die Kachel ein <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> , enthält eine <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Bewährte Methoden für mehrere Monitore anzeigen  
 Wenn Sie einen Computer, der über mehrere Monitore verfügt verwenden, sollten Sie die zuvor beschriebenen bewährten Methoden befolgen. Es gibt auch einige Leistungsaspekte für eine Konfiguration mit mehreren Monitoren.  
  
 Wenn Sie den Hintergrundpuffer erstellen, wird es auf einem bestimmten Gerät und der Adapter erstellt, aber WPF möglicherweise Frontpuffer für alle Adapter angezeigt. Adapter zum Aktualisieren des Frontpuffers Kopiervorgang kann sehr teuer sein. Unter Windows Vista, die konfiguriert ist, um die WDDM mit mehreren Videokarten und Verwenden einer `IDirect3DDevice9Ex` Gerät Frontpuffer auf einen anderen Adapter, aber dennoch die gleichen Grafikkarte vorhanden ist, keine Leistungseinbußen. Unter Windows XP und der XDDM mit mehreren Videokarten ist es jedoch beträchtliche Leistungseinbußen bei der Frontpuffer auf einen anderen Adapter als Hintergrundpuffer angezeigt wird. Weitere Informationen finden Sie unter [zwischen WPF und Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Zusammenfassung der cloudhostleistung von  
 Die folgende Tabelle zeigt die Leistung bei der Aktualisierung Frontpuffer als Funktion der Betriebssystem-Pixelformat und Surface Lockability. Die Frontpuffer und Hintergrundpuffer wird angenommen, dass auf dem Adapter. Je nach der Konfiguration des Adapters sind Hardwareupdates in der Regel viel schneller ist als Software-Updates.  
  
|Surface-Pixelformat|Windows Vista, WDDM und 9Ex|Weitere Windows Vista-Konfigurationen|Windows XP SP3 oder SP2 mit hotfix|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (nicht gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT_X8R8G8B8-(gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|**Hardwareupdate**|  
|D3DFMT_A8R8G8B8 (nicht gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT_A8R8G8B8-(gesperrt werden kann)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|Softwareupdate|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.D3DImage>
- [Interaktion zwischen WPF und Direct3D9](wpf-and-direct3d9-interoperation.md)
- [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
