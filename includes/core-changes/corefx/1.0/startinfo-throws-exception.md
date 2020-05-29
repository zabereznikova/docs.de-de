---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420426"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a><span data-ttu-id="930ff-101">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="930ff-101">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>

<span data-ttu-id="930ff-102">Das Lesen der <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für Prozesse, die Ihr Code nicht gestartet hat, löst eine <xref:System.InvalidOperationException> aus.</span><span class="sxs-lookup"><span data-stu-id="930ff-102">Reading the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start throws an <xref:System.InvalidOperationException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="930ff-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="930ff-103">Change description</span></span>

<span data-ttu-id="930ff-104">In .NET Framework wird beim Zugriff auf die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für Prozesse, die Ihr Code nicht gestartet hat, ein Dummy-<xref:System.Diagnostics.ProcessStartInfo>-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="930ff-104">In .NET Framework, accessing the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start returns a dummy <xref:System.Diagnostics.ProcessStartInfo> object.</span></span> <span data-ttu-id="930ff-105">Das Dummyobjekt enthält Standardwerte für alle seine Eigenschaften außer <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span><span class="sxs-lookup"><span data-stu-id="930ff-105">The dummy object contains default values for all of its properties except <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span></span>

<span data-ttu-id="930ff-106">Ab .NET Core 1.0 wird eine <xref:System.InvalidOperationException> ausgelöst, wenn Sie die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft für einen Prozess lesen, den Sie nicht gestartet haben (d. h. durch Aufrufen von <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="930ff-106">Starting in .NET Core 1.0, if you read the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for a process that you didn't start (that is, by calling <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), an <xref:System.InvalidOperationException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="930ff-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="930ff-107">Version introduced</span></span>

<span data-ttu-id="930ff-108">1.0</span><span class="sxs-lookup"><span data-stu-id="930ff-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="930ff-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="930ff-109">Recommended action</span></span>

<span data-ttu-id="930ff-110">Greifen Sie nicht für Prozesse, die Ihr Code nicht gestartet hat, auf die <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType>-Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="930ff-110">Do not access the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start.</span></span> <span data-ttu-id="930ff-111">Lesen Sie diese Eigenschaft z. B. nicht für Prozesse, die von <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="930ff-111">For example, don't read this property for processes returned by <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="930ff-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="930ff-112">Category</span></span>

<span data-ttu-id="930ff-113">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="930ff-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="930ff-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="930ff-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
