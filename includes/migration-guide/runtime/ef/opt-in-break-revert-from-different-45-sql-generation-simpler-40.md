---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497818"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5

#### <a name="details"></a>Details

Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL. Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.

#### <a name="suggestion"></a>Vorschlag

Dieses Feature ist standardmäßig deaktiviert. Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Transparent|
|Version|4.5.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
