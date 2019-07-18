---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804086"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>MEF-Kataloge implementieren IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul zu erstellen

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 implementieren MEF-Kataloge IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>-Objekt) zu erstellen. Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.|
|Vorschlag|MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Laufzeit|
