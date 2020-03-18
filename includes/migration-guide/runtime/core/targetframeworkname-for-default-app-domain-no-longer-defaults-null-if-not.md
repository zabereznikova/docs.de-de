---
ms.openlocfilehash: cbe1b32fa40e509f620845866c7a584e37f49a80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858618"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>TargetFrameworkName für die Standardanwendungsdomäne erhält nicht mehr standardmäßig den Wert NULL, wenn kein Wert festgelegt wurde

|   |   |
|---|---|
|Details|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> erhielt bereits in der Standardanwendungsdomäne den Wert NULL, sofern kein Wert explizit festgelegt wurde. Ab Version 4.6 weist die <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name>-Eigenschaft für die Standardanwendungsdomäne einen Standardwert auf, der von TargetFrameworkAttribute (sofern vorhanden) abgeleitet wird. Nicht standardmäßige Anwendungsdomänen erben ihr <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=name> weiterhin von der Standardanwendungsdomäne (die in Version 4.6 nicht standardmäßig auf NULL festgelegt ist), sofern sie nicht explizit außer Kraft gesetzt wird.|
|Vorschlag|Der Code sollte aktualisiert werden, um nicht davon abhängig zu sein, dass <xref:System.AppDomainSetup.TargetFrameworkName> standardmäßig NULL verwendet. Wenn es erforderlich ist, dass diese Eigenschaft weiterhin zu NULL ausgewertet wird, kann dieser Wert explizit festgelegt werden.|
|`Scope`|Edge|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
