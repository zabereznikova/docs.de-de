---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774343"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen

|   |   |
|---|---|
|Details|Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen. Für .NET Framework 4.5 wird Entity Framework 5 empfohlen. Bei EF 4.x in einem .NET Framework 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt. In .NET 4.5 wurden diese in eine andere Assembly verschoben, daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.|
|Vorschlag|Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Neuzuweisung|
