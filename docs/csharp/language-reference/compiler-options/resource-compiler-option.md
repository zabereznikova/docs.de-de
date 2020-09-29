---
description: -resource (C#-Compileroptionen)
title: -resource (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193776"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="ee2d3-103">-resource (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ee2d3-103">-resource (C# Compiler Options)</span></span>

<span data-ttu-id="ee2d3-104">Bettet die angegebene Ressource in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee2d3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee2d3-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee2d3-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="ee2d3-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="ee2d3-107">Die .NET-Ressourcendatei, die in die Ausgabedatei eingebettet werden soll</span><span class="sxs-lookup"><span data-stu-id="ee2d3-107">The .NET resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="ee2d3-108">`identifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="ee2d3-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="ee2d3-109">Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="ee2d3-110">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="ee2d3-111">`accessibility-modifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="ee2d3-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="ee2d3-112">Barrierefreiheit der Ressource: öffentlich oder privat.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="ee2d3-113">Der Standardwert ist public.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee2d3-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ee2d3-114">Remarks</span></span>  

 <span data-ttu-id="ee2d3-115">Verwenden Sie [-linkresource](./linkresource-compiler-option.md), um eine Ressource mit einer Assembly zu verknüpfen, anstatt die Ressourcendatei zur Ausgabedatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="ee2d3-116">Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mithilfe des C#-Compilers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="ee2d3-117">Geben Sie `private` als Modifizierer der Barrierefreiheit an.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="ee2d3-118">Außer `public` und `private` sind keine anderen Zugriffsmethoden zulässig.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="ee2d3-119">Wenn es sich bei `filename` um eine .NET-Ressourcendatei handelt, die beispielsweise von [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-119">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="ee2d3-120">Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee2d3-121">Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="ee2d3-122">**-res** ist die Kurzform von **-resource**.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="ee2d3-123">Die Reihenfolge der Ressourcen in der Ausgabedatei wird durch die in der Befehlszeile angegebene Reihenfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ee2d3-124">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="ee2d3-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ee2d3-125">Fügen Sie Ihrem Projekt eine Ressourcendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="ee2d3-126">Wählen Sie im **Projektmappen-Explorer** die Datei aus, die Sie einbetten möchten.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="ee2d3-127">Wählen Sie im Fenster **Eigenschaften** die Option **Buildvorgang** für die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="ee2d3-128">Legen Sie die Option **Buildvorgang** auf **Eingebettete Ressource** fest.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="ee2d3-129">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2d3-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee2d3-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee2d3-130">Example</span></span>  

 <span data-ttu-id="ee2d3-131">Kompilieren Sie `in.cs`, und fügen Sie die Ressourcendatei `rf.resource` an:</span><span class="sxs-lookup"><span data-stu-id="ee2d3-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee2d3-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee2d3-132">See also</span></span>

- [<span data-ttu-id="ee2d3-133">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ee2d3-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ee2d3-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee2d3-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
