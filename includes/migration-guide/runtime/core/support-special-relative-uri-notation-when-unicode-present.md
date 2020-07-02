---
ms.openlocfilehash: 08a9292c5a41e7b9b7c1bcc18ec96460de19863f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621185"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Unterstützen einer besonderen relativen URI-Notation, wenn Unicode vorhanden ist

#### <a name="details"></a>Details

<xref:System.Uri> löst keine <xref:System.NullReferenceException> mehr aus, wenn <xref:System.Uri.TryCreate%2A> für bestimmte relative URIs, die Unicode enthalten, aufgerufen wird. Am einfachsten können Sie die <xref:System.NullReferenceException> mit dem folgenden Code selbst nachvollziehen. Beide Anweisungen sind gleichwertig:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Zum Reproduzieren der <xref:System.NullReferenceException> müssen die folgenden Punkte zutreffen:<ul><li>Die URI muss als relativ angegeben werden, indem ihm „http:“ vorangestellt wird, anstatt dass „//“ auf ihn folgt.</li><li>Die URI muss als Prozentwert codiertes Unicode oder nicht reservierte Symbole enthalten.</li></ul>

#### <a name="suggestion"></a>Vorschlag

Benutzer, die zum Unterbinden relativer URIs von diesem Verhalten abhängig sind, sollten stattdessen beim Erstellen eines URI <xref:System.UriKind.Absolute?displayProperty=nameWithType> angeben.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
