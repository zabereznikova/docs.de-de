---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366851"
---
### <a name="exclude-specific-symbols"></a><span data-ttu-id="cb395-101">Bestimmte Symbole ausschließen</span><span class="sxs-lookup"><span data-stu-id="cb395-101">Exclude specific symbols</span></span>

<span data-ttu-id="cb395-102">Sie können bestimmte Symbole, z. b. Typen und Methoden, von der Analyse ausschließen.</span><span class="sxs-lookup"><span data-stu-id="cb395-102">You can exclude specific symbols, such as types and methods, from analysis.</span></span> <span data-ttu-id="cb395-103">Um z. b. anzugeben, dass die Regel nicht für Code innerhalb von Typen mit dem Namen ausgeführt `MyType` werden soll, fügen Sie das folgende Schlüssel-Wert-Paar in eine *Editor config* -Datei in Ihrem Projekt ein:</span><span class="sxs-lookup"><span data-stu-id="cb395-103">For example, to specify that the rule should not run on any code within types named `MyType`, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

<span data-ttu-id="cb395-104">Zulässige Symbol namens Formate im Optionswert (durch getrennt `|` ):</span><span class="sxs-lookup"><span data-stu-id="cb395-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="cb395-105">Nur Symbol Name (schließt alle Symbole mit dem Namen ein, unabhängig vom enthaltenden Typ oder Namespace).</span><span class="sxs-lookup"><span data-stu-id="cb395-105">Symbol name only (includes all symbols with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="cb395-106">Voll qualifizierte Namen im [Dokumentations-ID-Format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)des Symbols.</span><span class="sxs-lookup"><span data-stu-id="cb395-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings).</span></span> <span data-ttu-id="cb395-107">Jeder Symbol Name erfordert ein Symbol-Kind-Präfix, z `M:` . b. für Methoden, `T:` für Typen und `N:` für Namespaces.</span><span class="sxs-lookup"><span data-stu-id="cb395-107">Each symbol name requires a symbol-kind prefix, such as `M:` for methods, `T:` for types, and `N:` for namespaces.</span></span>
- <span data-ttu-id="cb395-108">`.ctor` für Konstruktoren und `.cctor` für statische Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="cb395-108">`.ctor` for constructors and `.cctor` for static constructors.</span></span>

<span data-ttu-id="cb395-109">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cb395-109">Examples:</span></span>

| <span data-ttu-id="cb395-110">Optionswert</span><span class="sxs-lookup"><span data-stu-id="cb395-110">Option Value</span></span> | <span data-ttu-id="cb395-111">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cb395-111">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | <span data-ttu-id="cb395-112">Entspricht allen Symbolen mit dem Namen `MyType` .</span><span class="sxs-lookup"><span data-stu-id="cb395-112">Matches all symbols named `MyType`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | <span data-ttu-id="cb395-113">Entspricht allen Symbolen mit dem Namen `MyType1` oder `MyType2` .</span><span class="sxs-lookup"><span data-stu-id="cb395-113">Matches all symbols named either `MyType1` or `MyType2`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | <span data-ttu-id="cb395-114">Entspricht einer bestimmten Methode `MyMethod` mit der angegebenen voll qualifizierten Signatur.</span><span class="sxs-lookup"><span data-stu-id="cb395-114">Matches specific method `MyMethod` with the specified fully qualified signature.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | <span data-ttu-id="cb395-115">Entspricht bestimmten Methoden `MyMethod1` und `MyMethod2` mit den jeweiligen voll qualifizierten Signaturen.</span><span class="sxs-lookup"><span data-stu-id="cb395-115">Matches specific methods `MyMethod1` and `MyMethod2` with the respective fully qualified signatures.</span></span> |
