---
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
ms.openlocfilehash: 8744d0f85859367ada51e4c44e767e681a3487bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="e9d6b-102">-resource (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e9d6b-102">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="e9d6b-103">Bettet die angegebene Ressource in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d6b-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e9d6b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e9d6b-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e9d6b-106">Die .NET Framework-Ressourcendatei, die in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="e9d6b-107">`identifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="e9d6b-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="e9d6b-108">Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="e9d6b-109">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="e9d6b-110">`accessibility-modifier` (optional)</span><span class="sxs-lookup"><span data-stu-id="e9d6b-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="e9d6b-111">Barrierefreiheit der Ressource: öffentlich oder privat.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="e9d6b-112">Der Standardwert ist „öffentlich“.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9d6b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d6b-113">Remarks</span></span>  
 <span data-ttu-id="e9d6b-114">Verwenden Sie [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), um eine Ressource mit einer Assembly zu verknüpfen, anstatt die Ressourcendatei zur Ausgabedatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-114">Use [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="e9d6b-115">Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mithilfe des C#-Compilers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="e9d6b-116">Geben Sie `private` als Modifizierer der Barrierefreiheit an.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="e9d6b-117">Außer `public` und `private` sind keine anderen Zugriffsmethoden zulässig.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="e9d6b-118">Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise von [resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="e9d6b-119">Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9d6b-120">Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="e9d6b-121">**-res** ist die Kurzform von **-resource**.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-121">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="e9d6b-122">Die Reihenfolge der Ressourcen in der Ausgabedatei wird durch die in der Befehlszeile angegebene Reihenfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e9d6b-123">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="e9d6b-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e9d6b-124">Fügen Sie Ihrem Projekt eine Ressourcendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-124">Add a resource file to your project.</span></span>  
  
2.  <span data-ttu-id="e9d6b-125">Wählen Sie im **Projektmappen-Explorer** die Datei aus, die Sie einbetten möchten.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3.  <span data-ttu-id="e9d6b-126">Wählen Sie im Fenster **Eigenschaften** die Option **Buildvorgang** für die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="e9d6b-127">Legen Sie die Option **Buildvorgang** auf **Eingebettete Ressource** fest.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="e9d6b-128">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9d6b-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9d6b-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9d6b-129">Example</span></span>  
 <span data-ttu-id="e9d6b-130">Kompilieren Sie `in.cs`, und fügen Sie die Ressourcendatei `rf.resource` an:</span><span class="sxs-lookup"><span data-stu-id="e9d6b-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9d6b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d6b-131">See Also</span></span>  
 [<span data-ttu-id="e9d6b-132">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="e9d6b-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="e9d6b-133">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e9d6b-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
