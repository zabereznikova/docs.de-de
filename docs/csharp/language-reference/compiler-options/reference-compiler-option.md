---
title: -reference (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: 3e6a999d528be111ba2b92886f4e6e3ebf185d5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173665"
---
# <a name="-reference-c-compiler-options"></a><span data-ttu-id="6a3fa-102">-reference (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="6a3fa-102">-reference (C# Compiler Options)</span></span>
<span data-ttu-id="6a3fa-103">Die Option **-reference** veranlasst den Compiler dazu, [öffentliche](../keywords/public.md) Typinformationen in der angegebenen Datei in das aktuelle Projekt zu importieren, sodass die Verweismetadaten aus den angegebenen Assemblydateien aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-103">The **-reference** option causes the compiler to import [public](../keywords/public.md) type information in the specified file into the current project, thus enabling you to reference metadata from the specified assembly files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a3fa-104">Syntax</span></span>  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a3fa-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6a3fa-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="6a3fa-106">Der Name einer Datei, die ein Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-106">The name of a file that contains an assembly manifest.</span></span> <span data-ttu-id="6a3fa-107">Fügen Sie die separate Option **-reference** für jede Datei ein, um mehr als eine Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-107">To import more than one file, include a separate **-reference** option for each file.</span></span>  
  
 `alias`  
 <span data-ttu-id="6a3fa-108">Ein gültiger C#-Bezeichner, der einen Stammnamespace darstellt, der alle Namespaces in der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-108">A valid C# identifier that will represent a root namespace that will contain all namespaces in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a3fa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a3fa-109">Remarks</span></span>  
 <span data-ttu-id="6a3fa-110">Fügen Sie die Option **-reference** für jede Datei ein, um mehr als eine Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-110">To import from more than one file, include a **-reference** option for each file.</span></span>  
  
 <span data-ttu-id="6a3fa-111">Die zu importierenden Dateien müssen ein Manifest enthalten. Die Ausgabedatei muss mit einer anderen [-target](./target-compiler-option.md)-Option als [-target:module](./target-module-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-111">The files you import must contain a manifest; the output file must have been compiled with one of the [-target](./target-compiler-option.md) options other than [-target:module](./target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="6a3fa-112">**-r** ist die Kurzform von **-reference**.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-112">**-r** is the short form of **-reference**.</span></span>  
  
 <span data-ttu-id="6a3fa-113">Verwenden Sie [-addmodule](./addmodule-compiler-option.md), um Metadaten aus einer Ausgabedatei zu importieren, die kein Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-113">Use [-addmodule](./addmodule-compiler-option.md) to import metadata from an output file that does not contain an assembly manifest.</span></span>  
  
 <span data-ttu-id="6a3fa-114">Wenn Sie auf eine Assembly (Assembly A) verweisen, die auf eine andere Assembly (Assembly B) verweist, müssen Sie auf Assembly B verweisen, wenn:</span><span class="sxs-lookup"><span data-stu-id="6a3fa-114">If you reference an assembly (Assembly A) that references another assembly (Assembly B), you will need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="6a3fa-115">Ein verwendeter Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-115">A type you use from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="6a3fa-116">Sie rufen ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode auf, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-116">You invoke a field, property, event, or method that has a return type or parameter type from Assembly B.</span></span>  
  
 <span data-ttu-id="6a3fa-117">Verwenden Sie [-lib](./lib-compiler-option.md), um das Verzeichnis anzugeben, in dem sich ein oder mehrere der Assemblyverweise befinden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-117">Use [-lib](./lib-compiler-option.md) to specify the directory in which one or more of your assembly references is located.</span></span> <span data-ttu-id="6a3fa-118">Der Artikel **-lib** erläutert auch die Verzeichnisse, in denen der Compiler nach Assemblys sucht.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-118">The **-lib** topic also discusses the directories in which the compiler searches for assemblies.</span></span>  
  
 <span data-ttu-id="6a3fa-119">Damit der Compiler einen Typ in einer Assembly, und nicht in einem Modul, erkennen kann, muss die Auflösung des Typs durch die Definition einer Instanz des Typs erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-119">In order for the compiler to recognize a type in an assembly, and not in a module, it needs to be forced to resolve the type, which you can do by defining an instance of the type.</span></span> <span data-ttu-id="6a3fa-120">Der Compiler verfügt über andere Möglichkeiten, Typnamen in einer Assembly aufzulösen. Beispielsweise wird beim Erben von einem Typ in einer Assembly der Typname vom Compiler erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-120">There are other ways to resolve type names in an assembly for the compiler: for example, if you inherit from a type in an assembly, the type name will then be recognized by the compiler.</span></span>  
  
 <span data-ttu-id="6a3fa-121">Manchmal ist es erforderlich, auf zwei verschiedene Versionen derselben Komponente aus einer Assembly heraus zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-121">Sometimes it is necessary to reference two different versions of the same component from within one assembly.</span></span> <span data-ttu-id="6a3fa-122">Verwenden Sie hierzu die Alias-Teiloption des Parameters **-reference** für jede Datei, um zwischen den beiden Dateien zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-122">To do this, use the alias suboption on the **-reference** switch for each file to distinguish between the two files.</span></span> <span data-ttu-id="6a3fa-123">Dieser Alias wird als Qualifizierer für den Namen der Komponente verwendet und wird für die Komponente in einer der Dateien aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-123">This alias will be used as a qualifier for the component name, and will resolve to the component in one of the files.</span></span>  
  
 <span data-ttu-id="6a3fa-124">Die csc-Antwortdatei (.rsp), welche auf häufig verwendete .NET Framework-Assemblys verweist, wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-124">The csc response (.rsp) file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="6a3fa-125">Verwenden Sie [-noconfig](./noconfig-compiler-option.md), wenn der Compiler „csc.rsp“ nicht verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-125">Use [-noconfig](./noconfig-compiler-option.md) if you do not want the compiler to use csc.rsp.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a3fa-126">Verwenden Sie in Visual Studio das Dialogfeld **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-126">In Visual Studio, use the **Add Reference** dialog box.</span></span> <span data-ttu-id="6a3fa-127">Weitere Informationen finden Sie unter [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span><span class="sxs-lookup"><span data-stu-id="6a3fa-127">For more information, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span> <span data-ttu-id="6a3fa-128">Um ein gleichwertiges Verhalten zwischen Hinzufügen von Verweisen mit `-reference` und Hinzufügen von Verweisen mithilfe des Dialogfelds **Verweis hinzufügen** sicherzustellen, legen Sie die Eigenschaft **Einbetten von Interop-Typen** für die Assembly, die Sie hinzufügen möchten, auf **FALSE** fest.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-128">To ensure equivalent behavior between adding references by using `-reference` and adding references by using the **Add Reference** dialog box, set the **Embed Interop Types** property to **False** for the assembly that you're adding.</span></span> <span data-ttu-id="6a3fa-129">Der Standardwert für diese Eigenschaft ist **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-129">**True** is the default value for the property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a3fa-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a3fa-130">Example</span></span>  
 <span data-ttu-id="6a3fa-131">Dieses Beispiel zeigt die Verwendung der Funktion [extern-Alias](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="6a3fa-131">This example shows how to use the [extern alias](../keywords/extern-alias.md) feature.</span></span>  
  
 <span data-ttu-id="6a3fa-132">Kompilieren Sie die Quelldatei, und importieren Sie Metadaten aus `grid.dll` und `grid20.dll`, die bereits zuvor kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-132">You compile the source file and import metadata from `grid.dll` and `grid20.dll`, which have been compiled previously.</span></span> <span data-ttu-id="6a3fa-133">Die beiden DLLs enthalten separate Versionen derselben Komponente, und Sie verwenden zwei **-reference**-Parameter mit Aliasoptionen, um die Quelldatei zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6a3fa-133">The two DLLs contain separate versions of the same component, and you use two **-reference** with alias options to compile the source file.</span></span> <span data-ttu-id="6a3fa-134">Die Optionen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="6a3fa-134">The options look like this:</span></span>  

```console
-reference:GridV1=grid.dll -reference:GridV2=grid20.dll  
```
  
 <span data-ttu-id="6a3fa-135">Dadurch werden die externen Aliase `GridV1` und `GridV2` eingerichtet, die Sie in Ihrem Programm über eine `extern`-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="6a3fa-135">This sets up the external aliases `GridV1` and `GridV2`, which you use in your program by means of an `extern` statement:</span></span>  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 <span data-ttu-id="6a3fa-136">Sobald dies geschehen ist, können Sie auf das Grid-Steuerelement von `grid.dll` verweisen, indem Sie dem Namen des Steuerelements wie folgt `GridV1` voranstellen:</span><span class="sxs-lookup"><span data-stu-id="6a3fa-136">Once this is done, you can refer to the grid control from `grid.dll` by prefixing the control name with `GridV1`, like this:</span></span>  
  
```csharp  
GridV1::Grid  
```  
  
 <span data-ttu-id="6a3fa-137">Darüber hinaus können Sie auf das Grid-Steuerelement von `grid20.dll` verweisen, indem Sie dem Namen des Steuerelements wie folgt `GridV2` voranstellen:</span><span class="sxs-lookup"><span data-stu-id="6a3fa-137">In addition, you can refer to the grid control from `grid20.dll` by prefixing the control name with `GridV2` like this:</span></span>  
  
```csharp  
GridV2::Grid
```  
  
## <a name="see-also"></a><span data-ttu-id="6a3fa-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a3fa-138">See also</span></span>

- [<span data-ttu-id="6a3fa-139">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6a3fa-139">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6a3fa-140">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6a3fa-140">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
