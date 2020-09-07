---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496571"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="fd51e-101">EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab</span><span class="sxs-lookup"><span data-stu-id="fd51e-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="fd51e-102">Details</span><span class="sxs-lookup"><span data-stu-id="fd51e-102">Details</span></span>

<span data-ttu-id="fd51e-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab.</span><span class="sxs-lookup"><span data-stu-id="fd51e-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="fd51e-104">NULL-Zeichen werden nicht von der <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd51e-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="fd51e-105">Die Änderung betrifft nur Apps, die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> verwenden, um <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess zu lesen, und die NULL-Zeichen als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd51e-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fd51e-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fd51e-106">Suggestion</span></span>

<span data-ttu-id="fd51e-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten sollten nach Möglichkeit aktualisiert werden, damit sie keine eingebetteten NULL-Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd51e-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="fd51e-108">name</span><span class="sxs-lookup"><span data-stu-id="fd51e-108">Name</span></span>    | <span data-ttu-id="fd51e-109">Wert</span><span class="sxs-lookup"><span data-stu-id="fd51e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fd51e-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="fd51e-110">Scope</span></span>   |<span data-ttu-id="fd51e-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fd51e-111">Edge</span></span>|
|<span data-ttu-id="fd51e-112">Version</span><span class="sxs-lookup"><span data-stu-id="fd51e-112">Version</span></span>|<span data-ttu-id="fd51e-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="fd51e-113">4.5.1</span></span>|
|<span data-ttu-id="fd51e-114">Typ</span><span class="sxs-lookup"><span data-stu-id="fd51e-114">Type</span></span>|<span data-ttu-id="fd51e-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fd51e-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fd51e-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fd51e-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
