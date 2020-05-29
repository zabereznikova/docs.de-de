---
title: Breaking Changes bei der Globalisierung
description: Listet die Breaking Changes bei der Globalisierung in .NET Core auf.
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702301"
---
# <a name="globalization-breaking-changes"></a>Breaking Changes bei der Globalisierung

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows](#globalization-apis-use-icu-libraries-on-windows) | 5.0 |
| [StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | 5.0 |
| [Gebietsschema „C“ wird dem invarianten Gebietsschema zugeordnet](#c-locale-maps-to-the-invariant-locale) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
