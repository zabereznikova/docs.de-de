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
# <a name="globalization-breaking-changes"></a><span data-ttu-id="84a48-103">Breaking Changes bei der Globalisierung</span><span class="sxs-lookup"><span data-stu-id="84a48-103">Globalization breaking changes</span></span>

<span data-ttu-id="84a48-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="84a48-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="84a48-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="84a48-105">Breaking change</span></span> | <span data-ttu-id="84a48-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="84a48-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="84a48-107">Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows</span><span class="sxs-lookup"><span data-stu-id="84a48-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="84a48-108">5.0</span><span class="sxs-lookup"><span data-stu-id="84a48-108">5.0</span></span> |
| [<span data-ttu-id="84a48-109">StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel</span><span class="sxs-lookup"><span data-stu-id="84a48-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="84a48-110">5.0</span><span class="sxs-lookup"><span data-stu-id="84a48-110">5.0</span></span> |
| [<span data-ttu-id="84a48-111">Gebietsschema „C“ wird dem invarianten Gebietsschema zugeordnet</span><span class="sxs-lookup"><span data-stu-id="84a48-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="84a48-112">3.0</span><span class="sxs-lookup"><span data-stu-id="84a48-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="84a48-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="84a48-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="84a48-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84a48-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
