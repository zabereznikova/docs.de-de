---
title: Laufzeit-Profilerstellung
description: Sehen Sie sich die Laufzeitprofil Erstellung in .net an. Hierbei handelt es sich um eine Methode zum Sammeln von Leistungsdaten in jedem Entwicklungs-oder
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters
- common language runtime, profiling
- Perfmon.exe
- System Monitor
- profiling
- runtime, profiling
- profiling applications
- Performance Console
ms.assetid: ccd68284-f3a8-47b8-bc3f-92e5fe3a1640
ms.openlocfilehash: fc88cc5c7c7655cf03573bae3935498a05496cc2
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803585"
---
# <a name="runtime-profiling"></a>Laufzeit-Profilerstellung
Die Profilerstellung ist eine Methode zum Sammeln von Leistungsdaten in einer Bereitstellung oder einem Bereitstellungsszenario. Dieser Abschnitt ist für Entwickler und Systemadministratoren vorgesehen, die Informationen zur Leistung der Anwendung erfassen möchten.  
  
## <a name="tracking-performance-using-the-performance-monitor-perfmonexe"></a>Verfolgen der Leistung mithilfe des Systemmonitors (Perfmon.exe)  
 Der System Monitor ist das einfachste Tool, mit dem Sie ein Profil für Ihre .NET Framework Anwendung erstellen können. Der System Monitor stellt Daten grafisch dar, die in den .NET Framework Leistungsindikatoren gefunden werden, die mit dem Common Language Runtime und dem Windows SDK installiert werden. Mithilfe dieser Leistungsindikatoren können Sie von der Speicherverwaltung bis zur JIT-Compilerleistung (JIT) sämtliche Informationen überwachen. Sie informieren Sie über die von der Anwendung verwendeten Ressourcen, die ein indirektes Maß für die Leistung der Anwendung sind. Verwenden Sie diese Leistungsindikatoren, um zu verstehen, wie die Anwendung intern funktioniert.  
  
#### <a name="to-run-perfmonexe-on-windows-vista-and-later-versions"></a>So führen Sie „Perfmon.exe“ unter Windows Vista und höheren Versionen aus  
  
1. Geben Sie an der Eingabeaufforderung **perfmon**ein. Die **Systemmonitor** -Konsole wird angezeigt.  
  
2. Klicken Sie im Ordner **Überwachungstools** auf **Systemmonitor**.  
  
3. Klicken Sie auf der Symbolleiste des Systemmonitors auf das Symbol **Hinzufügen** (das Pluszeichen), sofern es vorhanden ist. Wenn es nicht vorhanden ist, klicken Sie mit der rechten Maustaste im Überwachungsfenster, und wählen Sie dann die Option **Leistungsindikatoren hinzufügen** aus.  
  
     Dadurch wird das Dialogfeld **Leistungsindikatoren hinzufügen** geöffnet. Das Listenfeld **Verfügbare Indikatoren** zeigt die verfügbaren Leistungsobjekte an. Es gibt eine Reihe von vordefinierten Objekten für .NET Framework-Clientanwendungen, einschließlich der Objekte für die Speicherverwaltung (**.NET CLR-Speicher**), Interoperabilität (**.NET CLR-Interop**), Ausnahmebehandlung (**.NET CLR-Ausnahmen**) und für Multithreading (**.NET CLR-Sperren und Threads**). Jedes Leistungsobjekt umfasst eine Reihe von einzelnen Leistungsindikatoren. Eine Liste der im Systemmonitor verfügbaren Leistungsindikatoren finden Sie unter [Performance Counters](performance-counters.md)installiert werden.  
  
4. Aktivieren Sie das Kontrollkästchen neben dem Namen eines Leistungsobjekts, um die Liste der einzelnen Leistungsindikatoren anzuzeigen, die es unterstützt.  
  
5. Klicken Sie auf den Leistungsindikator, den Sie anzeigen möchten.  
  
6. Klicken Sie im Listenfeld **Instanzen des ausgewählten Objekts** auf, **\<All instances>** um anzugeben, dass Sie den Leistungsindikatoren für die Common Language Runtime Global (d. h. systemweit) überwachen möchten.  
  
     - oder -  
  
     Klicken Sie im Listenfeld **Instanzen des ausgewählten Objekts** auf einen Anwendungsnamen, um den Leistungsindikator für diese Anwendung zu überwachen.  
  
     Sie müssen zudem einen Registrierungsschlüssel ändern, um verschiedene Versionen der Laufzeit oder mehrere Clientanwendungen mit dem gleichen Namen zu unterscheiden. Weitere Informationen finden Sie unter [Performance Counters and In-Process Side-By-Side Applications](performance-counters-and-in-process-side-by-side-applications.md).  
  
> [!NOTE]
> Wenn neue Leistungsindikatoren installiert werden, während die Leistungskonsole ausgeführt wird, beenden Sie die Leistungskonsole und starten sie anschließend neu, damit die neuen Indikatoren angezeigt werden.  
  
 Wenn Sie für eine Assembly ein Profil erstellen möchten, die sich in einer Zone oder auf einer Remotefreigabe befindet, stellen Sie sicher, dass die Remoteassembly auf dem Computer über volle Vertrauenswürdigkeit verfügt, auf dem die Leistungsindikatoren ausgeführt werden. Ist die Vertrauenswürdigkeit der Assembly zu gering bemessen, funktionieren die Leistungsindikatoren nicht. Informationen zum Gewähren von Vertrauenswürdigkeit für verschiedene Zonen finden Sie unter [Caspol.exe (Code Access Security Policy-Tool)](../tools/caspol-exe-code-access-security-policy-tool.md).  
  
> [!NOTE]
> Auf Systemen, auf denen die .NET Framework 4 installiert ist, zeigt der System Monitor möglicherweise in einigen Kategorien, z. b. **.NET CLR-Daten** und **.NET CLR-Netzwerk**, keine Daten für Leistungsindikatoren für Anwendungen an, die mit dem .NET Framework 1,1 entwickelt wurden. Wenn dies der Fall ist, können Sie den System Monitor so konfigurieren, dass diese Daten angezeigt werden, indem Sie das [\<forcePerformanceCounterUniqueSharedMemoryReads>](../configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md) -Element der Konfigurationsdatei der Anwendung hinzufügen.  
  
## <a name="reading-and-creating-performance-counters-programmatically"></a>Programmgesteuertes Lesen und Erstellen von Leistungsindikatoren  
 Der .NET Framework stellt Klassen bereit, mit denen Sie Programm gesteuert auf dieselben Leistungsinformationen zugreifen können, die in der Leistungs Konsole verfügbar sind. Mithilfe dieser Klassen können Sie auch benutzerdefinierte Leistungsindikatoren erstellen. In der folgenden Tabelle werden einige der Leistungs Überwachungs Klassen beschrieben, die in der .NET Framework bereitgestellt werden.  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|<xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>|Stellt eine Windows NT-Leistungsindikatorkomponente dar. Verwenden Sie diese Klasse, um vordefinierte oder benutzerdefinierte Leistungsindikatoren zu lesen und Leistungsdaten für benutzerdefinierte Indikatoren zu veröffentlichen (schreiben).|  
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|Bietet verschiedene Methoden für die Interaktion mit Indikatoren und Kategorien von Indikatoren auf dem Computer.|  
|<xref:System.Diagnostics.PerformanceCounterInstaller?displayProperty=nameWithType>|Gibt einen Installer für die `PerformanceCounter` -Komponente an.|  
|<xref:System.Diagnostics.PerformanceCounterType?displayProperty=nameWithType>|Gibt die Formel zum Berechnen der `NextValue` -Methode für eine `PerformanceCounter`an.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Leistungsindikatoren](performance-counters.md)
