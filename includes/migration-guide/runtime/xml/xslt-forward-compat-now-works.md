---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497836"
---
### <a name="xslt-forward-compat-now-works"></a>Die Vorwärtskompatibilität für XSLT funktioniert jetzt

#### <a name="details"></a>Details

In .NET Framework 4 verursachte die XSLT 1.0-Vorwärtskompatibilität die folgenden Probleme:<ul><li>Beim Laden eines Stylesheets trat ein Fehler auf, wenn die Version auf 2.0 festgelegt war und der Parser ein unbekanntes XSLT 1.0-Konstrukt feststellte.</li><li>Das <code>xsl:sort</code>-Konstrukt konnte keine Daten sortieren, wenn die Stylesheetversion auf 1.1 festgelegt war.</li></ul>In .NET Framework 4.5 wurden diese Probleme behoben, und der XSLT 1.0-Vorwärtskompatibilitätsmodus funktioniert ordnungsgemäß.

#### <a name="suggestion"></a>Vorschlag

Die meisten Apps sollten zwar davon nicht betroffen sind, aber die Daten werden teilweise unterschiedlich sortiert, da das xsl:sort-Element jetzt berücksichtigt wird. Wenn <code>xsl:sort</code> in 1.1-Stylesheets verwendet wird, sollten Sie sicherstellen, dass die Apps nicht von der unsortierten Reihenfolge von Daten abhängig sind. Wenn Apps von dem in Version 4.0 enthaltenen Sortierverhalten abhängig ist, sollten Sie <code>xsl:sort</code> aus dem Stylesheet entfernen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
