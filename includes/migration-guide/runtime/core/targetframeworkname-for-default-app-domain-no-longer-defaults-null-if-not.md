---
ms.openlocfilehash: f955e270f709ddf6eea2e44bbcf386e372b9f6e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621317"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>TargetFrameworkName für die Standardanwendungsdomäne erhält nicht mehr standardmäßig den Wert NULL, wenn kein Wert festgelegt wurde

#### <a name="details"></a>Details

<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> erhielt bereits in der Standardanwendungsdomäne den Wert NULL, sofern kein Wert explizit festgelegt wurde. Ab Version 4.6 weist die <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>-Eigenschaft für die Standardanwendungsdomäne einen Standardwert auf, der von TargetFrameworkAttribute (sofern vorhanden) abgeleitet wird. Nicht standardmäßige Anwendungsdomänen erben ihr <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> weiterhin von der Standardanwendungsdomäne (die in Version 4.6 nicht standardmäßig auf NULL festgelegt ist), sofern sie nicht explizit außer Kraft gesetzt wird.

#### <a name="suggestion"></a>Vorschlag

Der Code sollte aktualisiert werden, um nicht davon abhängig zu sein, dass <xref:System.AppDomainSetup.TargetFrameworkName> standardmäßig NULL verwendet. Wenn es erforderlich ist, dass diese Eigenschaft weiterhin zu NULL ausgewertet wird, kann dieser Wert explizit festgelegt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
