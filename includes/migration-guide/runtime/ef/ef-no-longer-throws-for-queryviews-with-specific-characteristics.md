---
ms.openlocfilehash: c6c897c13c84ce4b2be21da18e5702365518f286
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620323"
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
