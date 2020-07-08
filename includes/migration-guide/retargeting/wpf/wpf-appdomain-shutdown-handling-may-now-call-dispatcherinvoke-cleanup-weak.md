---
ms.openlocfilehash: 8b804d23247b95381f3ff83bc12c32215a420fb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614609"
---
### <a name="wpf-appdomain-shutdown-handling-may-now-call-dispatcherinvoke-in-cleanup-of-weak-events"></a>Bei der Verarbeitung von WPF AppDomain-Herunterfahrvorgängen kann nun „Dispatcher.Invoke“ zur Bereinigung von schwachen Ereignissen aufgerufen werden

#### <a name="details"></a>Details

In .NET Framework 4.7.1 und früheren Versionen erstellt WPF möglicherweise während des Herunterfahrens von AppDomain einen <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType> im .NET-Finalizerthread.  Dies wurde in .NET Framework 4.7.2 und höheren Versionen korrigiert, indem nun bei der Bereinigung von schwachen Ereignissen Threads berücksichtigt werden.  Aus diesem Grund kann WPF <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> aufrufen, um den Bereinigungsprozess abzuschließen. In manchen Anwendungen kann diese Änderung des Finalizerzeitpunkts zu Ausnahmen beim Herunterfahren von AppDomain oder des Prozesses führen.  Dies tritt in der Regel bei Anwendungen auf, die die Verteiler, die auf Arbeitsthreads ausgeführt werden, nicht ordnungsgemäß herunterfahren, bevor der Prozess oder AppDomain heruntergefahren wird.  Bei solchen Anwendungen muss darauf geachtet werden, dass die Lebensdauer von Verteilern angemessen verwaltet wird.

#### <a name="suggestion"></a>Vorschlag

In .NET Framework 4.7.2 und höheren Versionen können Entwickler diesen Fix deaktivieren, um Probleme bei der Zeitsteuerung zu verringern (aber nicht zu verhindern), die aufgrund der Bereinigungsänderung auftreten können. Verwenden Sie zum Deaktivieren der Bereinigungsänderung das folgende AppContext-Flag.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotInvokeInWeakEventTableShutdownListener=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
