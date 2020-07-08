---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617191"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen

#### <a name="details"></a>Details

Die Version von Entity Framework muss mit der .NET Framework-Version übereinstimmen. Für .NET Framework 4.5 wird Entity Framework 5 empfohlen. Bei EF 4.x in einem .NET Framework 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt. In .NET Framework 4.5 wurden diese in eine andere Assembly verschoben. Daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.

#### <a name="suggestion"></a>Vorschlag

Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
