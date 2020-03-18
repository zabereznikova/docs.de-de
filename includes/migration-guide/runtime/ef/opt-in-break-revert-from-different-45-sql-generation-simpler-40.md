---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803276"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5

|   |   |
|---|---|
|Details|Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL. Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.|
|Vorschlag|Dieses Feature ist standardmäßig deaktiviert. Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|`Scope`|Transparent|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Laufzeit|
