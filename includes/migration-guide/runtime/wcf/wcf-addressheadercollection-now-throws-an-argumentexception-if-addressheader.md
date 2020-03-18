---
ms.openlocfilehash: d8c9cec723ec4e57fb4868cc95881be8eb4001b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857254"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a>Der WCF-Konstruktor AddressHeaderCollection löst jetzt eine ArgumentException aus, wenn ein addressHeader-Element den Wert NULL aufweist

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.1 löst der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>-Konstruktor eine <xref:System.ArgumentException> aus, wenn ein Element den Wert <code>null</code> aufweist. In .NET Framework 4.7 und früheren Versionen wird keine Ausnahme ausgelöst.|
|Vorschlag|Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|
