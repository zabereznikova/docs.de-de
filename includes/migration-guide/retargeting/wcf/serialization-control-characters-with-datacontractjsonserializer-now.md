---
ms.openlocfilehash: 2c532bf3778b940f68db859420dd12826e9da388
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77466040"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>Die Serialisierung von Steuerzeichen in DataContractJsonSerializer ist jetzt konform mit ECMAScript V6 und V8

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 und früheren Versionen serialisierte <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> einige besondere Steuerzeichen, wie etwa \b, \f und \t nicht in einer Weise, die mit den Standards ECMAScript V6 und V8 kompatibel ist. Ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel.|
|Vorschlag|Standardmäßig wird dieses neue Feature nur für Apps aktiviert, die für .NET Framework 4.7 konzipiert sind. Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der app.config- oder web.config-Datei die folgende Zeile hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li></ul>|
