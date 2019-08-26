---
title: -linkresource (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 454915454f3faf15933257f3e3e221afec51d0ee
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606753"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="3afea-102">-linkresource (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3afea-102">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="3afea-103">Erstellt einen Link zur .NET Framework-Ressource in der Ausgabedatei</span><span class="sxs-lookup"><span data-stu-id="3afea-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="3afea-104">Die Ressourcendateien wird nicht in die Ausgabedatei eingefügt.</span><span class="sxs-lookup"><span data-stu-id="3afea-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="3afea-105">Dies ist ein Unterschied zur Option [-resource](./resource-compiler-option.md), die eine Ressourcendatei in die Ausgabedatei einbettet.</span><span class="sxs-lookup"><span data-stu-id="3afea-105">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3afea-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3afea-106">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3afea-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="3afea-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="3afea-108">Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten</span><span class="sxs-lookup"><span data-stu-id="3afea-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="3afea-109">`identifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="3afea-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="3afea-110">Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird.</span><span class="sxs-lookup"><span data-stu-id="3afea-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="3afea-111">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="3afea-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="3afea-112">`accessibility-modifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="3afea-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="3afea-113">Barrierefreiheit der Ressource: öffentlich oder privat.</span><span class="sxs-lookup"><span data-stu-id="3afea-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="3afea-114">Der Standardwert ist „öffentlich“.</span><span class="sxs-lookup"><span data-stu-id="3afea-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3afea-115">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3afea-115">Remarks</span></span>  
 <span data-ttu-id="3afea-116">Verknüpfte Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mit den C#-Compiler erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3afea-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="3afea-117">Geben Sie `private` als Modifizierer der Barrierefreiheit an.</span><span class="sxs-lookup"><span data-stu-id="3afea-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="3afea-118">Außer `public` und `private` sind keine anderen Modifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="3afea-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="3afea-119">**-linkresource** erfordert eine andere [-target](./target-compiler-option.md)-Option als **-target:module**.</span><span class="sxs-lookup"><span data-stu-id="3afea-119">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="3afea-120">Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise von [resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich.</span><span class="sxs-lookup"><span data-stu-id="3afea-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="3afea-121">Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3afea-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3afea-122">Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3afea-122">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="3afea-123">Die in `filename` angegebene Datei kann jedes Format haben.</span><span class="sxs-lookup"><span data-stu-id="3afea-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="3afea-124">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3afea-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="3afea-125">Das zweite Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="3afea-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="3afea-126">Sie können dasselbe aber auch im Assemblylinker vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3afea-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="3afea-127">Das dritte Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="3afea-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="3afea-128">Weitere Informationen finden Sie unter [Al.exe (Assembly Linker-Tool)](../../../framework/tools/al-exe-assembly-linker.md) und [Arbeiten mit Assemblys und dem globalen Assemblycache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3afea-128">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="3afea-129">**-linkres** ist die Kurzform von **-linkresource**.</span><span class="sxs-lookup"><span data-stu-id="3afea-129">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="3afea-130">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3afea-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3afea-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3afea-131">Example</span></span>  
 <span data-ttu-id="3afea-132">Kompilieren Sie `in.cs` und verknüpfen Sie die Ressourcendatei `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="3afea-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="3afea-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3afea-133">Example</span></span>  
 <span data-ttu-id="3afea-134">Kompilieren Sie `A.cs` in eine DLL, verknüpfen Sie eine native DLL „n.dll“, und fügen Sie die Ausgabe in den globalen Assemblycache (GAC) ein.</span><span class="sxs-lookup"><span data-stu-id="3afea-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="3afea-135">In diesem Beispiel befinden sich sowohl „a.dll“ als auch „n.dll“ im GAC.</span><span class="sxs-lookup"><span data-stu-id="3afea-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="3afea-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3afea-136">Example</span></span>  
 <span data-ttu-id="3afea-137">In diesem Beispiel wird das Gleiche wie im vorherigen Beispiel erreicht, allerdings mithilfe von Assemblylinkeroptionen.</span><span class="sxs-lookup"><span data-stu-id="3afea-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3afea-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3afea-138">See also</span></span>

- [<span data-ttu-id="3afea-139">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="3afea-139">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3afea-140">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="3afea-140">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="3afea-141">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="3afea-141">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="3afea-142">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="3afea-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
