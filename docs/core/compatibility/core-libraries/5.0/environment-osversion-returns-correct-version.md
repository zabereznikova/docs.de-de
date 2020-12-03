---
title: 'Breaking Change: Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Environment.OSVersion die tatsächliche Version des Betriebssystems anstelle z. B. des Betriebssystems zurückgibt, das für die Anwendungskompatibilität ausgewählt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759566"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="2ad86-103">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="2ad86-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="2ad86-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt die tatsächliche Betriebssystemversion (OS) zurück, anstatt beispielsweise das Betriebssystem zurückzugeben, das für die Anwendungskompatibilität ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2ad86-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="2ad86-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2ad86-105">Change description</span></span>

<span data-ttu-id="2ad86-106">In früheren .NET-Versionen gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> eine Betriebssystemversion zurück, die möglicherweise falsch ist, wenn eine Anwendung im Windows-Kompatibilitätsmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ad86-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="2ad86-107">Weitere Informationen finden Sie in den [Hinweisen zur GetVersionExA-Funktion](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="2ad86-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="2ad86-108">Ab .NET 5.0 gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die tatsächliche Version des Betriebssystems zurück.</span><span class="sxs-lookup"><span data-stu-id="2ad86-108">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2ad86-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="2ad86-109">Reason for change</span></span>

<span data-ttu-id="2ad86-110">Benutzer dieser Eigenschaft erwarten, dass die tatsächliche Version des Betriebssystems zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2ad86-110">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="2ad86-111">Die meisten .NET-Apps geben die unterstützte Version nicht im Anwendungsmanifest an und verwenden daher die standardmäßig unterstützte Version des dotnet-Hosts.</span><span class="sxs-lookup"><span data-stu-id="2ad86-111">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="2ad86-112">Folglich ist der Kompatibilitätsshim für die ausgeführte App nur selten sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="2ad86-112">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="2ad86-113">Wenn Windows eine neue Version veröffentlicht und ein älterer dotnet-Host weiterhin verwendet wird, verwenden diese Apps möglicherweise eine falsche Betriebssystemversion.</span><span class="sxs-lookup"><span data-stu-id="2ad86-113">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="2ad86-114">Die Rückgabe der tatsächlichen Version entspricht eher den Erwartungen der Entwickler dieser API.</span><span class="sxs-lookup"><span data-stu-id="2ad86-114">Returning the actual version is more inline with developers' expectations of this API.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2ad86-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2ad86-115">Version introduced</span></span>

<span data-ttu-id="2ad86-116">5.0</span><span class="sxs-lookup"><span data-stu-id="2ad86-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2ad86-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="2ad86-117">Recommended action</span></span>

<span data-ttu-id="2ad86-118">Überprüfen und testen Sie den von <xref:System.Environment.OSVersion?displayProperty=nameWithType> verwendeten Code, um sicherzustellen, dass sich dieser wie gewünscht verhält.</span><span class="sxs-lookup"><span data-stu-id="2ad86-118">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2ad86-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2ad86-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
