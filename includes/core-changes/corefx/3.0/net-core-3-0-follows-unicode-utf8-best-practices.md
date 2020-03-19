---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568092"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="c8b8e-101">.NET Core 3.0 befolgt bewährte Unicode-Methoden beim Ersetzen von falsch formatierten UTF-8-Bytesequenzen</span><span class="sxs-lookup"><span data-stu-id="c8b8e-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="c8b8e-102">Wenn die <xref:System.Text.UTF8Encoding>-Klasse während einer Byte-zu-Zeichen-Transcodierung auf eine falsch formatierte UTF-8-Byte-Sequenz trifft, ersetzt sie diese Sequenz durch ein „�“-Zeichen (U+FFFD ERSETZUNGSZEICHEN) in der Ausgabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="c8b8e-103">.NET Core 3.0 unterscheidet sich von früheren Versionen von .NET Core und .NET Framework durch die Einhaltung der bewährten Unicode-Methoden für die Durchführung dieser Ersetzung während des Transcodierungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="c8b8e-104">Dies ist Teil einer größeren Maßnahme zur Verbesserung der UTF-8-Verarbeitung in .NET, auch bei den neuen Typen <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> und <xref:System.Text.Rune?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="c8b8e-105">Der Typ <xref:System.Text.UTF8Encoding> wurde mit einem verbesserten Verfahren für die Fehlerbehandlung versehen, sodass die Ausgabe konsistent mit den neu eingeführten Typen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c8b8e-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="c8b8e-106">Change description</span></span>

<span data-ttu-id="c8b8e-107">Ab .NET Core 3.0 führt die <xref:System.Text.UTF8Encoding>-Klasse bei der Transcodierung von Bytes in Zeichen Zeichenersetzung basierend auf bewährten Unicode-Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="c8b8e-108">Der verwendete Ersetzungsmechanismus wird durch [The Unicode Standard, Version 12.0, Abschnitt 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) unter der Überschrift _U+FFFD Substitution of Maximum Subparts_ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="c8b8e-109">Dieses Verhalten gilt _nur_, wenn die Eingabebytesequenz falsch formatierte UTF-8-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="c8b8e-110">Außerdem gilt: Wenn die <xref:System.Text.UTF8Encoding>-Instanz mit `throwOnInvalidBytes: true` erstellt wurde (siehe [UTF8Encoding-Konstruktordokumentation] (<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>)), wird die `UTF8Encoding`-Instanz weiterhin bei ungültiger Eingabe ausgelöst, anstatt U+FFFD -Ersetzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="c8b8e-111">Das folgende Beispiel veranschaulicht die Auswirkung dieser Änderung mit einer ungültigen 3-Byte-Eingabe:</span><span class="sxs-lookup"><span data-stu-id="c8b8e-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="c8b8e-112">Falsch formatierte 3-Byte-Eingabe</span><span class="sxs-lookup"><span data-stu-id="c8b8e-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="c8b8e-113">Ausgabe vor .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c8b8e-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="c8b8e-114">Ausgabe ab .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c8b8e-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="c8b8e-115">`[ FFFD FFFD ]` (2-Zeichen-Ausgabe)</span><span class="sxs-lookup"><span data-stu-id="c8b8e-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="c8b8e-116">`[ FFFD FFFD FFFD ]` (3-Zeichen-Ausgabe)</span><span class="sxs-lookup"><span data-stu-id="c8b8e-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="c8b8e-117">Diese 3-Zeichen-Ausgabe ist die bevorzugte Ausgabe gemäß _Tabelle 3-9_ der oben genannten PDF-Datei zum Unicode-Standard.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c8b8e-118">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c8b8e-118">Version introduced</span></span>

<span data-ttu-id="c8b8e-119">3.0</span><span class="sxs-lookup"><span data-stu-id="c8b8e-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c8b8e-120">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="c8b8e-120">Recommended action</span></span>

<span data-ttu-id="c8b8e-121">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8b8e-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="c8b8e-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c8b8e-122">Category</span></span>

<span data-ttu-id="c8b8e-123">CoreFx</span><span class="sxs-lookup"><span data-stu-id="c8b8e-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c8b8e-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c8b8e-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
