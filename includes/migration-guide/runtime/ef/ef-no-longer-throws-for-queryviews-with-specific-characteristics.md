---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497690"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>Entity Framework löst für QueryViews bei bestimmten Zeichen keine Ausnahmen mehr aus

#### <a name="details"></a>Details

Entity Framework löst keine <xref:System.StackOverflowException?displayProperty=fullName>-Ausnahme mehr aus, wenn eine App eine Abfrage ausführt, die ein QueryView-Element mit einer 0..1-Navigationseigenschaft umfasst und versucht, die verwandten Entitäten als Teil der Abfrage zu verwenden. (Z.B. durch Aufrufen von <code>.Include(e =&gt; e.RelatedNavProp)</code>.)

#### <a name="suggestion"></a>Vorschlag

Diese Änderung betrifft nur Code, der QueryViews mit 1-0..1-Beziehungen verwendet, wenn Abfragen ausgeführt werden, die .Include aufrufen. Diese Änderung verbessert die Zuverlässigkeit und sollte für beinahe alle Apps transparent sein. Falls jedoch ein unerwünschtes Verhalten auftritt, können Sie dieses Feature deaktivieren, indem Sie den folgenden Eintrag im <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei einfügen:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
