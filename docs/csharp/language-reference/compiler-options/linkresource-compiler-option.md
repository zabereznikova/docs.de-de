---
description: -linkresource (C#-Compileroptionen)
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
ms.openlocfilehash: 4efa0cbf286b40ad971bad66a7acce15e553eb39
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194101"
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="f1a9f-103">-linkresource (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f1a9f-103">-linkresource (C# Compiler Options)</span></span>

<span data-ttu-id="f1a9f-104">Erstellt einen Link zur .NET-Ressource in der Ausgabedatei</span><span class="sxs-lookup"><span data-stu-id="f1a9f-104">Creates a link to a .NET resource in the output file.</span></span> <span data-ttu-id="f1a9f-105">Die Ressourcendateien wird nicht in die Ausgabedatei eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-105">The resource file is not added to the output file.</span></span> <span data-ttu-id="f1a9f-106">Dies ist ein Unterschied zur Option [-resource](./resource-compiler-option.md), die eine Ressourcendatei in die Ausgabedatei einbettet.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-106">This differs from the [-resource](./resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a9f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1a9f-107">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1a9f-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="f1a9f-108">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="f1a9f-109">Die .NET-Ressourcendatei, die Sie mit der Assembly verknüpfen möchten</span><span class="sxs-lookup"><span data-stu-id="f1a9f-109">The .NET resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="f1a9f-110">`identifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="f1a9f-110">`identifier` (optional)</span></span>  
 <span data-ttu-id="f1a9f-111">Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-111">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="f1a9f-112">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-112">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="f1a9f-113">`accessibility-modifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="f1a9f-113">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="f1a9f-114">Barrierefreiheit der Ressource: öffentlich oder privat.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-114">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="f1a9f-115">Der Standardwert ist public.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-115">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a9f-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f1a9f-116">Remarks</span></span>  

 <span data-ttu-id="f1a9f-117">Verknüpfte Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mit den C#-Compiler erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-117">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="f1a9f-118">Geben Sie `private` als Modifizierer der Barrierefreiheit an.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-118">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="f1a9f-119">Außer `public` und `private` sind keine anderen Modifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-119">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="f1a9f-120">**-linkresource** erfordert eine andere [-target](./target-compiler-option.md)-Option als **-target:module**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-120">**-linkresource** requires one of the [-target](./target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="f1a9f-121">Wenn es sich bei `filename` um eine .NET-Ressourcendatei handelt, die beispielsweise von [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-121">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="f1a9f-122">Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-122">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f1a9f-123">Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-123">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="f1a9f-124">Die in `filename` angegebene Datei kann jedes Format haben.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-124">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="f1a9f-125">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-125">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="f1a9f-126">Das zweite Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-126">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="f1a9f-127">Sie können dasselbe aber auch im Assemblylinker vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-127">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="f1a9f-128">Das dritte Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-128">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="f1a9f-129">Weitere Informationen finden Sie unter [Al.exe (Assembly Linker-Tool)](../../../framework/tools/al-exe-assembly-linker.md) und [Arbeiten mit Assemblys und dem globalen Assemblycache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="f1a9f-129">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="f1a9f-130">**-linkres** ist die Kurzform von **-linkresource**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-130">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="f1a9f-131">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-131">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1a9f-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1a9f-132">Example</span></span>  

 <span data-ttu-id="f1a9f-133">Kompilieren Sie `in.cs` und verknüpfen Sie die Ressourcendatei `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="f1a9f-133">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="f1a9f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1a9f-134">Example</span></span>  

 <span data-ttu-id="f1a9f-135">Kompilieren Sie `A.cs` in eine DLL, verknüpfen Sie eine native DLL „n.dll“, und fügen Sie die Ausgabe in den globalen Assemblycache (GAC) ein.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-135">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="f1a9f-136">In diesem Beispiel befinden sich sowohl „a.dll“ als auch „n.dll“ im GAC.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-136">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="f1a9f-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1a9f-137">Example</span></span>  

 <span data-ttu-id="f1a9f-138">In diesem Beispiel wird das Gleiche wie im vorherigen Beispiel erreicht, allerdings mithilfe von Assemblylinkeroptionen.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-138">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1a9f-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1a9f-139">See also</span></span>

- [<span data-ttu-id="f1a9f-140">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f1a9f-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f1a9f-141">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="f1a9f-141">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="f1a9f-142">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="f1a9f-142">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="f1a9f-143">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f1a9f-143">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
