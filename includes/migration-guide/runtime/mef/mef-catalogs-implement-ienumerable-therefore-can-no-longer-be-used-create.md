---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496643"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>MEF-Kataloge implementieren IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul zu erstellen

#### <a name="details"></a>Details

Ab .NET Framework 4.5 implementieren MEF-Kataloge IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Objekt) zu erstellen. Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.

#### <a name="suggestion"></a>Vorschlag

MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
