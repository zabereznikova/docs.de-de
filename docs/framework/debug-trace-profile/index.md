---
title: Debuggen, Ablaufverfolgung und Profilerstellung
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff2be73b2cea563066f70ea2fe6d53840f718e75
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855282"
---
# <a name="debugging-tracing-and-profiling"></a>Debuggen, Ablaufverfolgung und Profilerstellung
Um eine .NET Framework-Anwendung debuggen zu können, müssen der Compiler und die Laufzeitumgebung so konfiguriert sein, dass ein Debugger an die Anwendung angefügt werden und der Debugger, wenn möglich, sowohl Symbole als auch Zeilenzuordnungen für die Anwendung und deren entsprechende Microsoft Intermediate Language (MSIL) erstellen kann. Nach dem Debuggen einer verwalteten Anwendung kann ein Profil für sie erstellt werden, um die Leistung zu verbessern. Bei einer Profilerstellung werden die Quellcodezeilen bewertet und beschrieben, die den am häufigsten ausgeführten Code generieren, und wird ermittelt, wie lange es dauert, diese auszuführen.  
  
 .NET Framework-Anwendungen lassen sich problemlos mit Visual Studio debuggen, das viele der Konfigurationsdetails verwaltet. Wenn Visual Studio nicht installiert ist, können Sie die Leistung von .NET Framework-Anwendungen mithilfe der Debuggingklassen im <xref:System.Diagnostics>-Namespace von .NET Framework prüfen und verbessern. Dieser Namespace enthält die Klassen <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.TraceSource> zum Nachverfolgen des Ausführungsablaufs und die Klassen <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> und <xref:System.Diagnostics.PerformanceCounter> für die Codeprofilierung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktivieren von JIT-attach Debugging](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 Zeigt, wie die Registrierung zu konfigurieren ist, um eine Debug-Engine an eine .NET Framework-Anwendung anzufügen (JIT-attach Debugging).  
  
 [Erleichtern des Debuggens für ein Abbild](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 Zeigt, wie die JIT-Verfolgung aktiviert und die Optimierung deaktiviert wird, damit sich eine Assembly einfacher debuggen lässt.  
  
 [Ablaufverfolgung und Instrumentieren von Anwendungen](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 Beschreibt, wie die Ausführung einer Anwendung überwacht und wie diese instrumentiert werden kann, um anzuzeigen, wie gut die Anwendung ausgeführt wird oder ob etwaige Fehler aufgetreten sind.  
  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 Beschreibt MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen), die Hilfsmittel für das Debuggen sind, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen über den Laufzeitzustand bereitzustellen.  
  
 [Verbessern des Debuggens mit den Debuggeranzeigeattributen](../../../docs/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes.md)  
 Beschreibt, wie der Entwickler eines Typs angeben kann, wie der Typ aussieht, wenn er in einem Debugger angezeigt wird.  
  
 [Leistungsindikatoren](../../../docs/framework/debug-trace-profile/performance-counters.md)  
 Beschreibt die Leistungsindikatoren, die Sie zum Überwachen der Leistung einer Anwendung verwenden können.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Debuggen von ASP.NET- und AJAX-Anwendungen](https://msdn.microsoft.com/library/9d531913-541b-47b8-864d-138021fca0c6)  
 Enthält Voraussetzungen und Anweisungen für das Debuggen einer ASP.NET-Anwendung während der Entwicklung oder nach der Bereitstellung.  
  
 [Entwicklungshandbuch](../../../docs/framework/development-guide.md)  
 Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.
