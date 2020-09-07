---
ms.openlocfilehash: e56d896f093d6cd28ed0d6640ba154e5d4593c6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497636"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="67db4-101">Die DTD-Entitätserweiterung „XmlTextReader“ ist auf 10.000.000 Zeichen beschränkt</span><span class="sxs-lookup"><span data-stu-id="67db4-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="67db4-102">Details</span><span class="sxs-lookup"><span data-stu-id="67db4-102">Details</span></span>

<span data-ttu-id="67db4-103">Die DTD-Entitätserweiterung ist jetzt auf 10.000.000 Zeichen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="67db4-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="67db4-104">Das Laden von XML-Dateien ohne DTD-Entitätserweiterung oder mit eingeschränkter DTD-Entitätserweiterung ist davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="67db4-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="67db4-105">Dateien mit DTD-Entitäten, die auf mehr als 10.000.000 Zeichen erweitert werden, können nicht geladen werden und lösen nun eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="67db4-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67db4-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="67db4-106">Suggestion</span></span>

<span data-ttu-id="67db4-107">Wenn das Limit der DTD-Entitätserweiterung von 10.000.000 zu niedrig ist, kann der Wert mit der <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>-Eigenschaft außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="67db4-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="67db4-108">Eine <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>-Klasse mit dem richtigen <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>-Wert kann an eine <code>XmlReader.Create</code>-Klasse übergeben werden, die <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> akzeptiert (d.h. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>).</span><span class="sxs-lookup"><span data-stu-id="67db4-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="67db4-109">name</span><span class="sxs-lookup"><span data-stu-id="67db4-109">Name</span></span>    | <span data-ttu-id="67db4-110">Wert</span><span class="sxs-lookup"><span data-stu-id="67db4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67db4-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="67db4-111">Scope</span></span>   |<span data-ttu-id="67db4-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="67db4-112">Edge</span></span>|
|<span data-ttu-id="67db4-113">Version</span><span class="sxs-lookup"><span data-stu-id="67db4-113">Version</span></span>|<span data-ttu-id="67db4-114">4.5</span><span class="sxs-lookup"><span data-stu-id="67db4-114">4.5</span></span>|
|<span data-ttu-id="67db4-115">Typ</span><span class="sxs-lookup"><span data-stu-id="67db4-115">Type</span></span>|<span data-ttu-id="67db4-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="67db4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="67db4-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="67db4-117">Affected APIs</span></span>

- <xref:System.Xml.XmlTextReader?displayProperty=nameWithType>
- <xref:System.Xml.XmlTextReader.%23ctor>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)>

<!--

#### Affected APIs

- `T:System.Xml.XmlTextReader`
- `M:System.Xml.XmlTextReader.#ctor`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.Xml.XmlNameTable)`

-->
