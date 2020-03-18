---
ms.openlocfilehash: 01c0689bbfb102f8f4d9455f9d258e8ea5515d9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859362"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Falsche Implementierung von MemberDescriptor.Equals

|   |   |
|---|---|
|Details|Die ursprüngliche Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode hat zwei verschiedene Zeichenfolgeneigenschaften der zu vergleichenden Objekte miteinander verglichen: den Kategorienamen und die Beschreibungszeichenfolge. Die Korrektur besteht darin, <xref:System.ComponentModel.MemberDescriptor.Category> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Category> des zweiten Objekts und <xref:System.ComponentModel.MemberDescriptor.Description> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Description> des zweiten Objekts zu vergleichen.|
|Vorschlag|Wenn Ihre Anwendung erfordert, dass <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> manchmal <code>false</code> zurückgibt, wenn Deskriptoren äquivalent sind, und sie als Zielplattform .NET Framework 4.6.2 verwendet, sind mehrere Optionen verfügbar:<ol><li>Nehmen Sie Codeänderungen vor, um die <xref:System.ComponentModel.MemberDescriptor.Category>- und <xref:System.ComponentModel.MemberDescriptor.Description>-Felder manuell zusätzlich zum Aufrufen der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode zu vergleichen.</li><li>Sie können diese Änderung deaktivieren, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Wenn Ihre Anwendung für .NET Framework 4.6.1 oder frühere Versionen konzipiert ist, unter .NET Framework 4.6.2 ausgeführt wird und Sie diese Änderung aktivieren möchten, können Sie den Kompatibilitätsschalter auf <code>false</code> festlegen, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|
