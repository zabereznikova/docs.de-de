---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665620"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="e54bc-104">Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien</span><span class="sxs-lookup"><span data-stu-id="e54bc-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="e54bc-105">Beim Veröffentlichen einer eigenständigen Anwendung wird die .NET Core-Laufzeit mit der Anwendung gebündelt.</span><span class="sxs-lookup"><span data-stu-id="e54bc-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="e54bc-106">Durch diese Bündelung wird die Menge des Inhalts der gepackten Anwendung beträchtlich erhöht.</span><span class="sxs-lookup"><span data-stu-id="e54bc-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="e54bc-107">Wenn Sie Ihre Anwendung bereitstellen, ist die Größe häufig ein wichtiger Faktor.</span><span class="sxs-lookup"><span data-stu-id="e54bc-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="e54bc-108">Anwendungsentwickler versuchen in der Regel, die Größe des Anwendungspakets so gering wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="e54bc-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="e54bc-109">Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Laufzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e54bc-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="e54bc-110">Diese nicht verwendeten Teile der Laufzeit sind unnötig und können aus der gepackten Anwendung abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="e54bc-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="e54bc-111">Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="e54bc-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="e54bc-112">Kürzen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e54bc-112">Trim your application</span></span>

<span data-ttu-id="e54bc-113">Im folgenden Beispiel wird gezeigt, wie Sie die Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) kürzen:</span><span class="sxs-lookup"><span data-stu-id="e54bc-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="e54bc-114">Zum Kürzen der Anwendung werden ihre Binärdateien untersucht, um die erforderlichen Laufzeitassemblys zu ermitteln und einen entsprechenden Graphen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e54bc-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="e54bc-115">Die verbleibenden Laufzeitassemblys, auf die nicht verwiesen wird, werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="e54bc-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="e54bc-116">Kürzungsprobleme bei Verwendung von Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e54bc-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="e54bc-117">In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl.</span><span class="sxs-lookup"><span data-stu-id="e54bc-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="e54bc-118">Beispielsweise kann dieses Problem bei einer Anwendung auftreten, die Spiegelung verwendet, da die Abhängigkeit von der Assembly nur zur Laufzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="e54bc-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="e54bc-119">Das Kürzen ist nur problematisch, wenn die Verwendung von Spiegelung von einer Laufzeitassembly abhängt, auf die nicht direkt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e54bc-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="e54bc-120">Beachten Sie, dass im Anwendungscode möglicherweise Spiegelung nicht direkt verwendet wird, diese jedoch von einer Drittanbieterassembly verwendet wird, auf die Sie verweisen.</span><span class="sxs-lookup"><span data-stu-id="e54bc-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="e54bc-121">Wenn der Code über Spiegelung auf eine API verweist und der Linker die Assembly nicht kürzen soll, die diese API enthält, können Sie die Projektdatei ändern, um die Assembly aus dem Kürzungsvorgang auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="e54bc-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="e54bc-122">Im folgenden Beispiel wird gezeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:</span><span class="sxs-lookup"><span data-stu-id="e54bc-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="e54bc-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e54bc-123">See also</span></span>

- [<span data-ttu-id="e54bc-124">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="e54bc-124">.NET Core application deployment</span></span>](index.md)
