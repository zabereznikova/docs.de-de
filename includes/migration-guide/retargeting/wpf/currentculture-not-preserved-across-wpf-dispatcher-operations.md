---
ms.openlocfilehash: bd656478a55856e676853e57f3e7386ea0aa0211
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614546"
---
### <a name="currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>CurrentCulture wird zwischen WPF-Dispatcher-Vorgängen nicht beibehalten

#### <a name="details"></a>Details

Ab .NET Framework 4.6 gehen Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>, die innerhalb eines <xref:System.Windows.Threading.Dispatcher?displayProperty=fullName>-Elements vorgenommen werden, am Ende des Verteilungsvorgangs verloren. Auf ähnliche Weise werden Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> außerhalb eines Verteilungsvorgangs möglicherweise nicht übernommen, wenn der Vorgang ausgeführt wird. In der Praxis bedeutet dies, dass Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> möglicherweise zwischen Rückrufen der WPF-Benutzeroberfläche und anderem Code in einer WPF-Anwendung nicht übertragen werden. Der Grund dafür ist eine Änderung in <xref:System.Threading.ExecutionContext?displayProperty=fullName>, durch die <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> im Ausführungskontext gespeichert werden. Diese Änderung betrifft Apps mit der Zielplattform .NET Framework 4.6 und höher. WPF-Verteilungsvorgänge speichern den Ausführungskontext, der dazu verwendet wurde, um den Vorgang zu beginnen und stellen den vorherigen Kontext wieder her, wenn der Vorgang abgeschlossen ist. Da <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> jetzt Bestandteil dieses Kontexts sind, bleiben innerhalb eines Dispatchervorgangs an ihnen vorgenommene Änderungen außerhalb des Vorgangs nicht erhalten.

#### <a name="suggestion"></a>Vorschlag

Von dieser Änderung betroffene Apps können dieses Problem möglicherweise umgehen, indem das gewünschte <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>- oder <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>-Element in einem Feld gespeichert wird und für alle Vorgangstexte der Verteilung (einschließlich der Rückrufereignishandler für Benutzeroberflächenereignisse) geprüft wird, ob das richtige <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>- und <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>-Element festgelegt ist. Da die ExecutionContext-Änderung, die dieser WPF-Änderung zugrunde liegt, nur Apps betrifft, die auf .NET Framework 4.6 oder höher ausgerichtet sind, kann dieser Fehler alternativ vermieden werden, indem .NET Framework 4.5.2 als Zielplattform verwendet wird. Apps mit der Zielplattform .NET Framework 4.6 oder höher können dieses Problem ebenfalls umgehen, indem die folgende Kompatibilitätsoption festgelegt wird:

<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>

Dieses Problem wurde von WPF in .NET Framework 4.6.2 behoben. Es wurde ebenfalls in .NET Framework 4.6 und 4.6.1 durch [KB 3139549](https://support.microsoft.com/kb/3139549) behoben. Apps mit der Zielplattform .NET Framework 4.6 oder höher erhalten automatisch das richtige Verhalten in WPF-Anwendungen (<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>), das über Dispatcher-Vorgänge hinweg beibehalten werden würde.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |
