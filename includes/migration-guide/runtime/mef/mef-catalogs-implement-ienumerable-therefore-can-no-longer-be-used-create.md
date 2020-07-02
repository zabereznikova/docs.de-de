---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620342"
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
