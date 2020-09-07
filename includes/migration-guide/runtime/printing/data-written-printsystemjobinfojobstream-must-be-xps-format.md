---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496843"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="a6c73-101">In PrintSystemJobInfo.JobStream geschriebene Daten müssen in XPS formatiert sein</span><span class="sxs-lookup"><span data-stu-id="a6c73-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="a6c73-102">Details</span><span class="sxs-lookup"><span data-stu-id="a6c73-102">Details</span></span>

<span data-ttu-id="a6c73-103">Die <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft macht den Stream eines Druckauftrags verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a6c73-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="a6c73-104">Der Benutzer kann Rohdaten an das zugrunde liegende Betriebssystem senden, das Komponenten druckt, indem es in diesen Stream schreibt. Ab .NET Framework 4.5 unter Windows 8 und höheren Windows-Betriebssystemversionen müssen in diesen Stream geschriebene Daten als Paketstream im XPS-Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a6c73-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a6c73-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a6c73-105">Suggestion</span></span>

<span data-ttu-id="a6c73-106">Zum Ausgeben der Druckinhalte können Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a6c73-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="a6c73-107">Verwenden Sie die <xref:System.Windows.Xps.XpsDocumentWriter>-Klasse, um Druckinhalte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="a6c73-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="a6c73-108">Dies ist die empfohlene Alternative.</span><span class="sxs-lookup"><span data-stu-id="a6c73-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="a6c73-109">Stellen Sie sicher, dass die Daten, die an den von der <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft zurückgegebenen Stream gesendet werden, im XPS-Format als Paketstream vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a6c73-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="a6c73-110">name</span><span class="sxs-lookup"><span data-stu-id="a6c73-110">Name</span></span>    | <span data-ttu-id="a6c73-111">Wert</span><span class="sxs-lookup"><span data-stu-id="a6c73-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a6c73-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="a6c73-112">Scope</span></span>   |<span data-ttu-id="a6c73-113">Gering</span><span class="sxs-lookup"><span data-stu-id="a6c73-113">Minor</span></span>|
|<span data-ttu-id="a6c73-114">Version</span><span class="sxs-lookup"><span data-stu-id="a6c73-114">Version</span></span>|<span data-ttu-id="a6c73-115">4.5</span><span class="sxs-lookup"><span data-stu-id="a6c73-115">4.5</span></span>|
|<span data-ttu-id="a6c73-116">Typ</span><span class="sxs-lookup"><span data-stu-id="a6c73-116">Type</span></span>|<span data-ttu-id="a6c73-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a6c73-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a6c73-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a6c73-118">Affected APIs</span></span>

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
