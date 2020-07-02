---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620223"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="3ef00-101">EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab</span><span class="sxs-lookup"><span data-stu-id="3ef00-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="3ef00-102">Details</span><span class="sxs-lookup"><span data-stu-id="3ef00-102">Details</span></span>

<span data-ttu-id="3ef00-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab.</span><span class="sxs-lookup"><span data-stu-id="3ef00-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="3ef00-104">NULL-Zeichen werden nicht von der <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ef00-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="3ef00-105">Die Änderung betrifft nur Apps, die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> verwenden, um <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess zu lesen, und die NULL-Zeichen als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ef00-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3ef00-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3ef00-106">Suggestion</span></span>

<span data-ttu-id="3ef00-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten sollten nach Möglichkeit aktualisiert werden, damit sie keine eingebetteten NULL-Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ef00-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="3ef00-108">name</span><span class="sxs-lookup"><span data-stu-id="3ef00-108">Name</span></span>    | <span data-ttu-id="3ef00-109">Wert</span><span class="sxs-lookup"><span data-stu-id="3ef00-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3ef00-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="3ef00-110">Scope</span></span>   |<span data-ttu-id="3ef00-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3ef00-111">Edge</span></span>|
|<span data-ttu-id="3ef00-112">Version</span><span class="sxs-lookup"><span data-stu-id="3ef00-112">Version</span></span>|<span data-ttu-id="3ef00-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3ef00-113">4.5.1</span></span>|
|<span data-ttu-id="3ef00-114">Typ</span><span class="sxs-lookup"><span data-stu-id="3ef00-114">Type</span></span>|<span data-ttu-id="3ef00-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3ef00-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ef00-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3ef00-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
