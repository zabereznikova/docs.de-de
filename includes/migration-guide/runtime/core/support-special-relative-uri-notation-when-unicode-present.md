---
ms.openlocfilehash: 841cb06bf94844d9f4da9dc33e60bad0d43dcd84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997619"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Unterstützen einer besonderen relativen URI-Notation, wenn Unicode vorhanden ist

|   |   |
|---|---|
|Details|<xref:System.Uri> löst keine <xref:System.NullReferenceException> mehr aus, wenn <xref:System.Uri.TryCreate%2A> für bestimmte relative URIs, die Unicode enthalten, aufgerufen wird. Am einfachsten können Sie die <xref:System.NullReferenceException> mit dem folgenden Code selbst nachvollziehen. Beide Anweisungen sind gleichwertig:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Zum Reproduzieren der <xref:System.NullReferenceException> müssen die folgenden Punkte zutreffen:<ul><li>Die URI muss als relativ angegeben werden, indem ihm „http:“ vorangestellt wird, anstatt dass „//“ auf ihn folgt.</li><li>Die URI muss als Prozentwert codiertes Unicode oder nicht reservierte Symbole enthalten.</li></ul>|
|Vorschlag|Benutzer, die zum Unterbinden relativer URIs von diesem Verhalten abhängig sind, sollten stattdessen beim Erstellen eines URI <xref:System.UriKind.Absolute?displayProperty=nameWithType> angeben.|
|`Scope`|Edge|
|Version|4.7.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
