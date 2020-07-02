---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620353"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="61a79-101">In PrintSystemJobInfo.JobStream geschriebene Daten müssen in XPS formatiert sein</span><span class="sxs-lookup"><span data-stu-id="61a79-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="61a79-102">Details</span><span class="sxs-lookup"><span data-stu-id="61a79-102">Details</span></span>

<span data-ttu-id="61a79-103">Die <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft macht den Stream eines Druckauftrags verfügbar.</span><span class="sxs-lookup"><span data-stu-id="61a79-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="61a79-104">Der Benutzer kann Rohdaten an das zugrunde liegende Betriebssystem senden, das Komponenten druckt, indem es in diesen Stream schreibt. Ab .NET Framework 4.5 unter Windows 8 und höheren Windows-Betriebssystemversionen müssen in diesen Stream geschriebene Daten als Paketstream im XPS-Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="61a79-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61a79-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="61a79-105">Suggestion</span></span>

<span data-ttu-id="61a79-106">Zum Ausgeben der Druckinhalte können Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="61a79-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="61a79-107">Verwenden Sie die <xref:System.Windows.Xps.XpsDocumentWriter>-Klasse, um Druckinhalte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="61a79-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="61a79-108">Dies ist die empfohlene Alternative.</span><span class="sxs-lookup"><span data-stu-id="61a79-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="61a79-109">Stellen Sie sicher, dass die Daten, die an den von der <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft zurückgegebenen Stream gesendet werden, im XPS-Format als Paketstream vorliegen.</span><span class="sxs-lookup"><span data-stu-id="61a79-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="61a79-110">name</span><span class="sxs-lookup"><span data-stu-id="61a79-110">Name</span></span>    | <span data-ttu-id="61a79-111">Wert</span><span class="sxs-lookup"><span data-stu-id="61a79-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61a79-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="61a79-112">Scope</span></span>   |<span data-ttu-id="61a79-113">Gering</span><span class="sxs-lookup"><span data-stu-id="61a79-113">Minor</span></span>|
|<span data-ttu-id="61a79-114">Version</span><span class="sxs-lookup"><span data-stu-id="61a79-114">Version</span></span>|<span data-ttu-id="61a79-115">4.5</span><span class="sxs-lookup"><span data-stu-id="61a79-115">4.5</span></span>|
|<span data-ttu-id="61a79-116">Typ</span><span class="sxs-lookup"><span data-stu-id="61a79-116">Type</span></span>|<span data-ttu-id="61a79-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="61a79-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="61a79-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="61a79-118">Affected APIs</span></span>

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
