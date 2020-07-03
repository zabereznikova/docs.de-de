---
title: Mehrfachdateiassemblys
description: Verwenden Sie Mehrfachdateiassemblys, die auf .NET ausgerichtet sind, mithilfe des Befehlszeilencompilers oder in Visual Studio mit Visual C++. Eine Datei in der Assembly muss das Assemblymanifest enthalten.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104632"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="4ebbd-104">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="4ebbd-104">Multifile assemblies</span></span>

<span data-ttu-id="4ebbd-105">Sie können Mehrfachdateiassemblys für das .NET Framework mit Befehlszeilencompiler oder mit Visual Studio und Visual C++ erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-105">You can create multifile assemblies that target the .NET Framework using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="4ebbd-106">Eine Datei in der Assembly muss das Assemblymanifest enthalten.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-106">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="4ebbd-107">Eine Assembly, die eine Anwendung startet, muss außerdem einen Einstiegspunkt wie z. B. die Methoden `Main` oder `WinMain` enthalten.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-107">An assembly that starts an application must also contain an entry point, such as a `Main` or `WinMain` method.</span></span>

<span data-ttu-id="4ebbd-108">Angenommen, Sie verfügen über eine Anwendung, die die beiden Codemodule *Client.cs* und *Stringer.cs* enthält.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-108">For example, suppose you have an application that contains two code modules, *Client.cs* and *Stringer.cs*.</span></span> <span data-ttu-id="4ebbd-109">*Stringer.cs* erstellt den `myStringer`-Namespace, auf den im Code von *Client.cs* verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-109">*Stringer.cs* creates the `myStringer` namespace that is referenced by the code in *Client.cs*.</span></span> <span data-ttu-id="4ebbd-110">*Client.cs* enthält die `Main`-Methode, die der Einstiegspunkt der Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-110">*Client.cs* contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="4ebbd-111">In diesem Beispiel kompilieren Sie die zwei Codemodule und erstellen dann eine dritte Datei, die das Assemblymanifest enthält, das die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-111">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="4ebbd-112">Das Assemblymanifest verweist sowohl auf das Modul *Client* als auch auf *Stringer*.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-112">The assembly manifest references both the *Client* and *Stringer* modules.</span></span>

> [!NOTE]
> <span data-ttu-id="4ebbd-113">Mehrfachdateiassemblys können nur einen Einstiegspunkt haben, auch wenn die Assembly über mehrere Codemodule verfügt.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-113">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="4ebbd-114">Es gibt mehrere Gründe, sich für eine Mehrfachdateiassembly zu entscheiden:</span><span class="sxs-lookup"><span data-stu-id="4ebbd-114">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="4ebbd-115">Das Kombinieren von Modulen, die in unterschiedlichen Sprachen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-115">To combine modules written in different languages.</span></span> <span data-ttu-id="4ebbd-116">Dies ist der häufigste Grund für das Erstellen einer Mehrfachdateiassembly.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-116">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="4ebbd-117">Die Optimierung des Herunterladens einer Anwendung durch das Einfügen selten verwendeter Typen in ein Modul, das nur wenn nötig heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-117">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ebbd-118">Wenn Sie eine Anwendung erstellen, die mit dem `<object>`-Tag mit Microsoft Internet Explorer heruntergeladen wird, ist es wichtig, dass Sie Mehrfachdateiassemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-118">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="4ebbd-119">In diesem Szenario erstellen Sie eine von Ihren Codemodulen getrennte Datei, die nur das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-119">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="4ebbd-120">Internet Explorer lädt zunächst das Assemblymanifest herunter und erstellt anschließend Arbeitsthreads, um alle weiteren erforderlichen Module bzw. Assemblys herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-120">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="4ebbd-121">Während des Downloads der Datei, die das Assemblymanifest enthält, reagiert Internet Explorer nicht auf Eingaben des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-121">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="4ebbd-122">Je kleiner die Datei ist, die das Assemblymanifest enthält, desto kürzer ist die Zeitspanne, in der Internet Explorer nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-122">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="4ebbd-123">Das Kombinieren von Codemodulen, die von mehreren Entwicklern geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-123">To combine code modules written by several developers.</span></span> <span data-ttu-id="4ebbd-124">Obwohl jeder Entwickler jedes Codemodul in eine Assembly kompilieren kann, kann dies dazu führen, dass einige Teile öffentlich gemacht werden, die aber nicht verfügbar gemacht werden, wenn alle Module in eine Mehrfachdateiassembly integriert werden.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-124">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="4ebbd-125">Sobald Sie die Assembly erstellt haben, können Sie die Datei signieren, die das Assemblymanifest enthält. Dadurch wird gleichzeitig die Assembly signiert. Alternativ können Sie der Datei und der Assembly auch einen starken Namen geben und sie in den globalen Assemblycache einfügen.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-125">Once you create the assembly, you can sign the file that contains the assembly manifest, and hence the assembly, or you can give the file and the assembly a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ebbd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ebbd-126">See also</span></span>

- [<span data-ttu-id="4ebbd-127">How to: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="4ebbd-127">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="4ebbd-128">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="4ebbd-128">Program with assemblies</span></span>](../../standard/assembly/index.md)
