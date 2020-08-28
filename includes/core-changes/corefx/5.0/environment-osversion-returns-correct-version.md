---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558176"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="229c5-101">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="229c5-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="229c5-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt die tatsächliche Betriebssystemversion (OS) zurück, anstatt beispielsweise das Betriebssystem zurückzugeben, das für die Anwendungskompatibilität ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="229c5-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="229c5-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="229c5-103">Change description</span></span>

<span data-ttu-id="229c5-104">In früheren .NET-Versionen gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> eine Betriebssystemversion zurück, die möglicherweise falsch ist, wenn eine Anwendung im Windows-Kompatibilitätsmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="229c5-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="229c5-105">Weitere Informationen finden Sie in den [Hinweisen zur GetVersionExA-Funktion](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="229c5-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="229c5-106">Ab .NET 5.0 gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die tatsächliche Version des Betriebssystems zurück.</span><span class="sxs-lookup"><span data-stu-id="229c5-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="229c5-107">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="229c5-107">Reason for change</span></span>

<span data-ttu-id="229c5-108">Benutzer dieser Eigenschaft erwarten, dass die tatsächliche Version des Betriebssystems zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="229c5-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="229c5-109">Die meisten .NET-Apps geben die unterstützte Version nicht im Anwendungsmanifest an und verwenden daher die standardmäßig unterstützte Version des dotnet-Hosts.</span><span class="sxs-lookup"><span data-stu-id="229c5-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="229c5-110">Folglich ist der Kompatibilitätsshim für die ausgeführte App nur selten sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="229c5-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="229c5-111">Wenn Windows eine neue Version veröffentlicht und ein älterer dotnet-Host weiterhin verwendet wird, verwenden diese Apps möglicherweise eine falsche Betriebssystemversion.</span><span class="sxs-lookup"><span data-stu-id="229c5-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="229c5-112">Die Rückgabe der tatsächlichen Version entspricht eher den Erwartungen der Entwickler dieser API.</span><span class="sxs-lookup"><span data-stu-id="229c5-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="229c5-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="229c5-113">Version introduced</span></span>

<span data-ttu-id="229c5-114">5.0</span><span class="sxs-lookup"><span data-stu-id="229c5-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="229c5-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="229c5-115">Recommended action</span></span>

<span data-ttu-id="229c5-116">Überprüfen und testen Sie den von <xref:System.Environment.OSVersion?displayProperty=nameWithType> verwendeten Code, um sicherzustellen, dass sich dieser wie gewünscht verhält.</span><span class="sxs-lookup"><span data-stu-id="229c5-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="229c5-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="229c5-117">Category</span></span>

<span data-ttu-id="229c5-118">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="229c5-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="229c5-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="229c5-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
