---
ms.openlocfilehash: 8aae403e3f23d3bfc755140b2ac29d757f10f753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451464"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Verbesserung der Datenbindung für KeyedCollection

|   |   |
|---|---|
|Details|Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.|
|Vorschlag|Damit eine Anwendung für eine ältere Version von dieser Änderung profitiert, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Hauptversion|
|Version|4.8|
|Typ|Laufzeit|
