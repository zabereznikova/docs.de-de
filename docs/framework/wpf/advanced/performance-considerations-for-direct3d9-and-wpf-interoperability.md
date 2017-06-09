---
title: "&#220;berlegungen zur Leistung f&#252;r die Interoperabilit&#228;t zwischen Direct3D9 und WPF | Microsoft Docs"
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
  - "Direct3D9 [WPF-Interoperabilität], Leistung"
  - "WPF, Direct3D9-Interopleistung"
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# &#220;berlegungen zur Leistung f&#252;r die Interoperabilit&#228;t zwischen Direct3D9 und WPF
Sie können Direct3D9\-Inhalt mit der <xref:System.Windows.Interop.D3DImage>\-Klasse hosten.  Das Hosting von Direct3D9\-Inhalt kann sich auf die Leistung der Anwendung auswirken.  In diesem Thema werden bewährte Methoden zur Leistungsoptimierung beim Hosten von Direct3D9\-Inhalt in einer WPF\-Anwendung \(Windows Presentation Foundation\) beschrieben.  Zu diesen bewährten Methoden zählen u. a. die Verwendung von <xref:System.Windows.Interop.D3DImage> sowie die bewährten Methoden bei der Verwendung von Windows Vista, Windows XP und Multimonitor\-Anzeigen.  
  
> [!NOTE]
>  Codebeispiele, in denen diese bewährten Methoden veranschaulicht werden, finden Sie unter [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## Sparsame Verwendung von D3DImage  
 In einer <xref:System.Windows.Interop.D3DImage>\-Instanz gehosteter Direct3D9\-Inhalt kann nicht so schnell gerendert werden wie in einer reinen Direct3D\-Anwendung.  Das Kopieren der Oberfläche und Leeren des Befehlspuffers können kostenintensive Vorgänge sein.  In dem Maße wie die Anzahl der <xref:System.Windows.Interop.D3DImage>\-Instanzen zunimmt, finden mehr Löschvorgänge statt und die Leistung verschlechtert sich.  Deshalb sollten Sie <xref:System.Windows.Interop.D3DImage> sparsam verwenden.  
  
## Bewährte Methoden unter Windows Vista  
 Um eine optimale Leistung unter Windows Vista mit einer Anzeige zu erreichen, die für die Verwendung von WDDM \(Windows Display Driver Model, Windows\-Anzeigetreibermodell\) konfiguriert wird, erstellen Sie eine eigene Direct3D9\-Oberfläche auf einem `IDirect3DDevice9Ex`\-Gerät.  Dadurch wird die Oberflächenfreigabe aktiviert.  Die Videokarte muss die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES`\- und `D3DCAPS2_CANSHARERESOURCE`\-Treiberoptionen unter Windows Vista unterstützen.  Alle anderen Einstellungen führen dazu, dass die Oberfläche mithilfe von Software kopiert wird, was zu einer erheblichen Leistungseinschränkung führt.  
  
> [!NOTE]
>  Falls Windows Vista eine Anzeige bietet, die für die Verwendung von XDDM \(Windows XP Display Driver Model, Windows XP\-Anzeigetreibermodell\) konfiguriert ist, wird die Oberfläche immer mithilfe der Software konfiguriert, unabhängig von den Einstellungen.  Mit den entsprechenden Einstellungen und der entsprechenden Videokarte erleben Sie bei Verwendung von WDDM eine Leistungssteigerung unter Windows Vista, da die Oberflächenkopiervorgänge in der Hardware durchgeführt werden.  
  
## Bewährte Methoden unter Windows XP  
 Um eine optimale Leistung unter Windows XP zu erreichen, das XDDM verwendet, erstellen Sie eine Oberfläche, die gesperrt werden kann und die sich beim Aufruf der `IDirect3DSurface9::GetDC`\-Methode richtig verhält.  Intern überträgt die `BitBlt`\-Methode die Oberfläche über die Hardwaregeräte hinweg.  Die `GetDC`\-Methode funktioniert bei XRGB\-Oberflächen immer.  Wenn auf dem Clientcomputer jedoch Windows XP SP3 oder SP2 ausgeführt wird und auch der Hotfix für die Funktion für überlappende Fenster installiert wurde, funktioniert diese Methode nur für ARGB\-Oberflächen.  Die Videokarte muss die `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES`\-Treiberoption unterstützen.  
  
 Eine 16\-Bit\-Desktopanzeigetiefe kann die Leistung erheblich reduzieren.  Ein 32\-Bit\-Desktop wird empfohlen.  
  
 Wenn Sie für Windows Vista und Windows XP entwickeln, testen Sie die Leistung unter Windows XP.  Ein Problem besteht darin, unter Windows XP keinen Videospeicher mehr zur Verfügung zu haben.  Zudem belegt <xref:System.Windows.Interop.D3DImage> unter Windows XP aufgrund einer erforderlichen zusätzlichen Videospeicherkopie mehr Videospeicher und Bandbreite als Windows Vista WDDM.  Deshalb ist zu erwarten, dass die Leistung unter Windows XP für die gleiche Videohardware schlechter ist als unter Windows Vista.  
  
> [!NOTE]
>  XDDM steht sowohl unter Windows XP als auch unter Windows Vista zur Verfügung, WDDM jedoch nur unter Windows Vista.  
  
## Allgemeine bewährte Methoden  
 Wenn Sie das Gerät erstellen, verwenden Sie das `D3DCREATE_MULTITHREADED`\-Erstellungsflag.  Dadurch wird zwar die Leistung reduziert, das WPF\-Renderingsystem ruft jedoch auf diesem Gerät Methoden von einem anderen Thread auf.  Sie sollten das Sperrprotokoll ordnungsgemäß befolgen, damit nicht zwei Threads gleichzeitig auf das Gerät zugreifen.  
  
 Falls das Rendering auf einem von der WPF verwalteten Thread ausgeführt wird, wird empfohlen, das Gerät mit dem `D3DCREATE_FPU_PRESERVE`\-Erstellungsflag zu erstellen.  Ohne diese Einstellung kann das D3D\-Rendering die Genauigkeit von WPF\-Vorgängen mit doppelter Genauigkeit reduzieren und zu Rendering\-Problemen führen.  
  
 Die Unterteilung eines <xref:System.Windows.Interop.D3DImage> ist schnell, sofern es sich nicht um eine nicht\-pow2\-Oberfläche ohne Hardwareunterstützung handelt, oder falls Sie ein <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> unterteilen, das <xref:System.Windows.Interop.D3DImage> enthält.  
  
## Bewährte Methoden für Multimonitor\-Anzeigen  
 Wenn Sie einen Computer mit mehreren Monitoren verwenden, sollten Sie die zuvor beschriebenen bewährten Methoden befolgen.  Es gibt auch einige zusätzliche Leistungsüberlegungen für eine Multimonitor\-Konfiguration.  
  
 Wenn Sie den Hintergrundpuffer erstellen, wird er auf einem speziellen Gerät und Adapter erstellt. WPF kann jedoch den Frontpuffer auf einem beliebigen Adapter anzeigen.  Das Kopieren über mehrere Adapter hinweg zum Zwecke der Frontpufferaktualisierung kann sehr kostenintensiv sein.  Unter Windows Vista, das für die Verwendung der WDDM mit mehreren Videokarten und mit einem `IDirect3DDevice9Ex`\-Gerät konfiguriert ist, gibt es keine Leistungseinbußen, falls sich der Frontpuffer auf einem anderen Adapter befindet, es sich jedoch weiterhin um dieselbe Videokarte handelt.  Unter Windows XP und der XDDM mit mehreren Videokarten gibt es jedoch erhebliche Leistungseinbußen, wenn der Frontpuffer auf einem anderen Adapter als dem Hintergrundpuffer angezeigt wird.  Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## Leistungszusammenfassung  
 In der folgenden Tabelle wird die Leistung der Frontpufferaktualisierung als Funktion des Betriebssystems, des Pixelformats und der Oberflächensperrung dargestellt.  Es wird angenommen, dass sich der Frontpuffer und der Hintergrundpuffer auf demselben Adapter befinden.  Je nach Adapterkonfiguration sind Hardwareupdates im Allgemeinen viel schneller als Softwareupdates.  
  
|Oberflächenpixelformat|Windows Vista, WDDM und 9Ex|Weitere Windows Vista\-Konfigurationen|Windows XP SP3 oder SP2 w\/ hotfix|Windows XP SP2|  
|----------------------------|---------------------------------|--------------------------------------------|----------------------------------------|--------------------|  
|D3DFMT\_X8R8G8B8 \(nicht sperrbar\)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT\_X8R8G8B8 \(sperrbar\)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|**Hardwareupdate**|  
|D3DFMT\_A8R8G8B8 \(nicht sperrbar\)|**Hardwareupdate**|Softwareupdate|Softwareupdate|Softwareupdate|  
|D3DFMT\_A8R8G8B8 \(sperrbar\)|**Hardwareupdate**|Softwareupdate|**Hardwareupdate**|Softwareupdate|  
  
## Siehe auch  
 <xref:System.Windows.Interop.D3DImage>   
 [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)   
 [Exemplarische Vorgehensweise: Erstellen von Direct3D9\-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten von Direct3D9\-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)