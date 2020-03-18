---
ms.openlocfilehash: d35de48dd22003c851cf5dba9e8517ec48b9217b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567785"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a>Gebietsschema „C“ wird dem invarianten Gebietsschema zugeordnet

.NET Core 2.2 und frühere Versionen hängen von dem ICU-Standardverhalten ab, das das Gebietsschema „C“ zum Gebietsschema „en_US_POSIX“ zuordnet. Das Gebietsschema „en_US_POSIX“ weist ein unerwünschtes Sortierverhalten auf, da es keine Zeichenfolgenvergleiche ohne Berücksichtigung der Groß-/Kleinschreibung unterstützt. Da einige Linux-Verteilungen das Gebietsschema „C“ als Standardgebietsschema festlegen, kam es bei einigen Benutzern zu unerwartetem Verhalten.

#### <a name="change-description"></a>Änderungsbeschreibung

Die Zuordnung des Gebietsschemas „C“ wurde ab .NET Core 3.0 geändert, sodass das invariante Gebietsschema anstelle von „en_US_POSIX“ verwendet wird. Die Zuordnung des Gebietsschemas „C“ zum invarianten Gebietsschema wird zur Gewährleistung der Konsistenz auch auf Windows angewendet.

Die Zuordnung von „C“ zu „en_US_POSIX“ sorgte bei Kunden für Verwirrung, da „en_US_POSIX“ keine Sortier- und Suchvorgänge für Zeichenfolgen ohne Beachtung der Groß-/Kleinschreibung unterstützt. Da das Gebietsschema „C“ in einigen Linux-Verteilungen als Standardgebietsschema verwendet wird, trat dieses unerwünschte Verhalten bei Kunden mit diesen Betriebssystemen auf.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

### <a name="recommended-action"></a>Empfohlene Aktion

Es ist keine spezifische Maßnahme erforderlich. Sie sollten lediglich über die Änderung informiert sein. Diese Änderung wirkt sich nur auf Anwendungen aus, die die Zuordnung des Gebietsschemas „C“ verwenden.

### <a name="category"></a>Kategorie

Globalisierung

### <a name="affected-apis"></a>Betroffene APIs

Diese Änderung wirkt sich auf alle Sortierungs- und Kultur-APIs aus.

<!--

-->
