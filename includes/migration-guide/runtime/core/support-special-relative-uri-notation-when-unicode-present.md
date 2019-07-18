---
ms.openlocfilehash: c8a6870a9d34889dd8f5305035744bfc63be6af6
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856991"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Unterstützen einer besonderen relativen URI-Notation, wenn Unicode vorhanden ist

|   |   |
|---|---|
|Details|<xref:System.Uri> löst beim Aufrufen von <xref:System.Uri.TryCreate%2A> für bestimmte relative URIs, die Unicode enthalten, keine <xref:System.NullReferenceException> mehr aus. Die einfachste Reproduktion der <xref:System.NullReferenceException> finden Sie nachstehend, wobei die beiden Anweisungen äquivalent sind:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Zum Reproduzieren der <xref:System.NullReferenceException> müssen die folgenden Punkte zutreffen:<ul><li>Die URI muss als relativ angegeben werden, indem ihm „http:“ vorangestellt wird, anstatt dass „//“ auf ihn folgt.</li><li>Die URI muss als Prozentwert codiertes Unicode oder nicht reservierte Symbole enthalten.</li></ul>|
|Vorschlag|Benutzer, die zum Unterbinden relativer URIs von diesem Verhalten abhängig sind, sollten stattdessen beim Erstellen eines URI <xref:System.UriKind.Absolute?displayProperty=nameWithType> angeben.|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|

