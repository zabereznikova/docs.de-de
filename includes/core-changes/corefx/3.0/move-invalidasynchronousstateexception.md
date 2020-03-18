---
ms.openlocfilehash: 19359422f79f8240676b0057c7391f6b06f961ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147548"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="68d23-101">InvalidAsynchronousStateException in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="68d23-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="68d23-102">Die <xref:System.ComponentModel.InvalidAsynchronousStateException>-Klasse wurde verschoben.</span><span class="sxs-lookup"><span data-stu-id="68d23-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="68d23-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="68d23-103">Change description</span></span>

<span data-ttu-id="68d23-104">In .NET Core 2.2 und früheren Versionen befand sich die <xref:System.ComponentModel.InvalidAsynchronousStateException>-Klasse in der *System.ComponentModel.TypeConverter*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="68d23-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="68d23-105">Seit .NET Core 3.0 befindet sie sich in der *System.ComponentModel.Primitives*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="68d23-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="68d23-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="68d23-106">Version introduced</span></span>

<span data-ttu-id="68d23-107">3.0</span><span class="sxs-lookup"><span data-stu-id="68d23-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="68d23-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="68d23-108">Recommended action</span></span>

<span data-ttu-id="68d23-109">Diese Änderung betrifft nur Anwendungen, welche die Reflektion zum Laden von <xref:System.ComponentModel.InvalidAsynchronousStateException> durch Aufrufen einer Methode wie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> oder eine Überladung von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> nutzen, bei der vorausgesetzt wird, dass sich der Typ in einer bestimmten Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="68d23-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="68d23-110">Ist dies der Fall, muss die im Methodenaufruf referenzierte Assembly entsprechend dem neuen Assemblyspeicherort des Typs aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="68d23-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="68d23-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="68d23-111">Category</span></span>

<span data-ttu-id="68d23-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="68d23-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="68d23-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="68d23-113">Affected APIs</span></span>

<span data-ttu-id="68d23-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="68d23-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
