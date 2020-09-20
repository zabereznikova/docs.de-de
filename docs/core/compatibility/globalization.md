---
title: Breaking Changes bei der Globalisierung
description: Listet die Breaking Changes bei der Globalisierung in .NET Core auf.
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065063"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="0cd01-103">Breaking Changes bei der Globalisierung</span><span class="sxs-lookup"><span data-stu-id="0cd01-103">Globalization breaking changes</span></span>

<span data-ttu-id="0cd01-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="0cd01-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="0cd01-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="0cd01-105">Breaking change</span></span> | <span data-ttu-id="0cd01-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0cd01-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="0cd01-107">Geänderte Unicode-Kategorie für einige Zeichen in Lateinisch-1</span><span class="sxs-lookup"><span data-stu-id="0cd01-107">Unicode category changed for some Latin-1 characters</span></span>](#unicode-category-changed-for-some-latin-1-characters) | <span data-ttu-id="0cd01-108">5.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-108">5.0</span></span> |
| [<span data-ttu-id="0cd01-109">Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows</span><span class="sxs-lookup"><span data-stu-id="0cd01-109">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="0cd01-110">5.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-110">5.0</span></span> |
| [<span data-ttu-id="0cd01-111">StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel</span><span class="sxs-lookup"><span data-stu-id="0cd01-111">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="0cd01-112">5.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-112">5.0</span></span> |
| [<span data-ttu-id="0cd01-113">Gebietsschema „C“ wird dem invarianten Gebietsschema zugeordnet</span><span class="sxs-lookup"><span data-stu-id="0cd01-113">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="0cd01-114">3.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="0cd01-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-115">.NET 5.0</span></span>

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="0cd01-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0cd01-116">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
