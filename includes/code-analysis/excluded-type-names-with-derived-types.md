---
ms.openlocfilehash: 4125df1d64fe7f3f2eb1eb4a821ed46c8270c95f
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97532089"
---
### <a name="exclude-specific-types-and-their-derived-types"></a><span data-ttu-id="15eee-101">Bestimmte Typen und deren abgeleitete Typen ausschließen</span><span class="sxs-lookup"><span data-stu-id="15eee-101">Exclude specific types and their derived types</span></span>

<span data-ttu-id="15eee-102">Sie können bestimmte Typen und deren abgeleitete Typen aus der Analyse ausschließen.</span><span class="sxs-lookup"><span data-stu-id="15eee-102">You can exclude specific types and their derived types from analysis.</span></span> <span data-ttu-id="15eee-103">Um z. b. anzugeben, dass die Regel nicht für Methoden innerhalb von Typen mit dem Namen `MyType` und den abgeleiteten Typen ausgeführt werden soll, fügen Sie das folgende Schlüssel-Wert-Paar zu einer *editorconfig* -Datei in Ihrem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="15eee-103">For example, to specify that the rule should not run on any methods within types named `MyType` and their derived types, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

<span data-ttu-id="15eee-104">Zulässige Symbol namens Formate im Optionswert (durch getrennt `|` ):</span><span class="sxs-lookup"><span data-stu-id="15eee-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="15eee-105">Nur Typname (schließt alle Typen mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace).</span><span class="sxs-lookup"><span data-stu-id="15eee-105">Type name only (includes all types with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="15eee-106">Voll qualifizierte Namen im [Dokumentations-ID-Format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)des Symbols mit einem optionalen `T:` Präfix.</span><span class="sxs-lookup"><span data-stu-id="15eee-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings), with an optional `T:` prefix.</span></span>

<span data-ttu-id="15eee-107">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="15eee-107">Examples:</span></span>

| <span data-ttu-id="15eee-108">Optionswert</span><span class="sxs-lookup"><span data-stu-id="15eee-108">Option Value</span></span> | <span data-ttu-id="15eee-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="15eee-109">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | <span data-ttu-id="15eee-110">Entspricht allen Typen `MyType` mit dem Namen und allen abgeleiteten Typen.</span><span class="sxs-lookup"><span data-stu-id="15eee-110">Matches all types named `MyType` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | <span data-ttu-id="15eee-111">Entspricht allen Typen `MyType1` `MyType2` mit dem Namen oder und allen abgeleiteten Typen.</span><span class="sxs-lookup"><span data-stu-id="15eee-111">Matches all types named either `MyType1` or `MyType2` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | <span data-ttu-id="15eee-112">Entspricht einem bestimmten Typ `MyType` mit dem angegebenen voll qualifizierten Namen und allen abgeleiteten Typen.</span><span class="sxs-lookup"><span data-stu-id="15eee-112">Matches specific type `MyType` with given fully qualified name and all of its derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | <span data-ttu-id="15eee-113">Vergleicht bestimmte Typen `MyType1` und `MyType2` mit den jeweiligen voll qualifizierten Namen und allen abgeleiteten Typen.</span><span class="sxs-lookup"><span data-stu-id="15eee-113">Matches specific types `MyType1` and `MyType2` with the respective fully qualified names, and all of their derived types.</span></span> |
