---
ms.openlocfilehash: beb869208e8d48d762d94b5989a558fa2f1aaf29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622010"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Verbesserung der Datenbindung für KeyedCollection

#### <a name="details"></a>Details

Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.

#### <a name="suggestion"></a>Vorschlag

Damit eine Anwendung für eine ältere Version von dieser Änderung profitiert, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.8|
|Typ|Laufzeit|
