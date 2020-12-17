---
title: 'Breaking Change: Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Environment.OSVersion die tatsächliche Version des Betriebssystems anstelle z. B. des Betriebssystems zurückgibt, das für die Anwendungskompatibilität ausgewählt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009520"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="70e69-103">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="70e69-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="70e69-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt die tatsächliche Betriebssystemversion (OS) zurück, anstatt beispielsweise das Betriebssystem zurückzugeben, das für die Anwendungskompatibilität ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="70e69-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="70e69-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="70e69-105">Change description</span></span>

<span data-ttu-id="70e69-106">In früheren .NET-Versionen gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> eine Betriebssystemversion zurück, die möglicherweise falsch ist, wenn eine Anwendung im Windows-Kompatibilitätsmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="70e69-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="70e69-107">Weitere Informationen finden Sie in den [Hinweisen zur GetVersionExA-Funktion](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="70e69-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span> <span data-ttu-id="70e69-108">Unter macOS gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die zugrunde liegende Darwin-Kernelversion zurück.</span><span class="sxs-lookup"><span data-stu-id="70e69-108">On macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the underlying Darwin kernel version.</span></span>

<span data-ttu-id="70e69-109">Ab .NET 5.0 gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die tatsächliche Version des Windows- oder macOS-Betriebssystems zurück.</span><span class="sxs-lookup"><span data-stu-id="70e69-109">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system for Windows and macOS.</span></span>

<span data-ttu-id="70e69-110">In der folgenden Tabelle werden die Verhaltensunterschiede aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="70e69-110">The following table shows the difference in behavior.</span></span>

|  | <span data-ttu-id="70e69-111">Frühere .NET-Versionen</span><span class="sxs-lookup"><span data-stu-id="70e69-111">Previous .NET versions</span></span> | <span data-ttu-id="70e69-112">.NET 5 und höher</span><span class="sxs-lookup"><span data-stu-id="70e69-112">.NET 5+</span></span> |
|--|------------------------|---------|
| <span data-ttu-id="70e69-113">Windows</span><span class="sxs-lookup"><span data-stu-id="70e69-113">Windows</span></span> | <span data-ttu-id="70e69-114">6.2.9200.0</span><span class="sxs-lookup"><span data-stu-id="70e69-114">6.2.9200.0</span></span> | <span data-ttu-id="70e69-115">10.0.19042.0</span><span class="sxs-lookup"><span data-stu-id="70e69-115">10.0.19042.0</span></span> |
| <span data-ttu-id="70e69-116">macOS</span><span class="sxs-lookup"><span data-stu-id="70e69-116">macOS</span></span> | <span data-ttu-id="70e69-117">19.6.0.0</span><span class="sxs-lookup"><span data-stu-id="70e69-117">19.6.0.0</span></span> | <span data-ttu-id="70e69-118">10.15.7</span><span class="sxs-lookup"><span data-stu-id="70e69-118">10.15.7</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="70e69-119">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="70e69-119">Reason for change</span></span>

<span data-ttu-id="70e69-120">Benutzer dieser Eigenschaft erwarten, dass die tatsächliche Version des Betriebssystems zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="70e69-120">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="70e69-121">Die meisten .NET-Apps geben die unterstützte Version nicht im Anwendungsmanifest an und verwenden daher die standardmäßig unterstützte Version des dotnet-Hosts.</span><span class="sxs-lookup"><span data-stu-id="70e69-121">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="70e69-122">Folglich ist der Kompatibilitätsshim für die ausgeführte App nur selten sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="70e69-122">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="70e69-123">Wenn Windows eine neue Version veröffentlicht und ein älterer dotnet-Host weiterhin verwendet wird, verwenden diese Apps möglicherweise eine falsche Betriebssystemversion.</span><span class="sxs-lookup"><span data-stu-id="70e69-123">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="70e69-124">Die Rückgabe der tatsächlichen Version entspricht eher den Erwartungen der Entwickler dieser API.</span><span class="sxs-lookup"><span data-stu-id="70e69-124">Returning the actual version is more inline with developers' expectations of this API.</span></span>

<span data-ttu-id="70e69-125">Mit der Einführung von <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> und <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5.0 wurde <xref:System.Environment.OSVersion?displayProperty=nameWithType> geändert, um mehr Konsistenz für Windows und macOS einzuführen.</span><span class="sxs-lookup"><span data-stu-id="70e69-125">With the introduction of <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType>, and <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> was changed to be consistent for Windows and macOS.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="70e69-126">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="70e69-126">Version introduced</span></span>

<span data-ttu-id="70e69-127">5.0</span><span class="sxs-lookup"><span data-stu-id="70e69-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="70e69-128">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="70e69-128">Recommended action</span></span>

<span data-ttu-id="70e69-129">Überprüfen und testen Sie den von <xref:System.Environment.OSVersion?displayProperty=nameWithType> verwendeten Code, um sicherzustellen, dass sich dieser wie gewünscht verhält.</span><span class="sxs-lookup"><span data-stu-id="70e69-129">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="70e69-130">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="70e69-130">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
