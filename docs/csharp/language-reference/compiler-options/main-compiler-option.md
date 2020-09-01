---
description: -main (C#-Compileroptionen)
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 61e63de8082a335b448ffee1ae35170d3a1cf6b4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125266"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="fccd8-103">-main (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="fccd8-103">-main (C# Compiler Options)</span></span>

<span data-ttu-id="fccd8-104">Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="fccd8-104">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="fccd8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fccd8-105">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="fccd8-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="fccd8-106">Arguments</span></span>
 `class`  
 <span data-ttu-id="fccd8-107">Der Typ, der die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="fccd8-107">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="fccd8-108">Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fccd8-108">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="fccd8-109">Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.</span><span class="sxs-lookup"><span data-stu-id="fccd8-109">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fccd8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fccd8-110">Remarks</span></span>

<span data-ttu-id="fccd8-111">Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fccd8-111">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="fccd8-112">Diese Option wird verwendet, wenn eine *EXE*-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="fccd8-112">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="fccd8-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="fccd8-113">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="fccd8-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="fccd8-114">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="fccd8-115">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="fccd8-115">Click the **Application** property page.</span></span>

3. <span data-ttu-id="fccd8-116">Ändern Sie die Eigenschaft **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="fccd8-116">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="fccd8-117">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="fccd8-117">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="fccd8-118">So legen Sie diese Compileroption fest, indem Sie die *CSPROJ*-Datei manuell bearbeiten</span><span class="sxs-lookup"><span data-stu-id="fccd8-118">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="fccd8-119">Sie können diese Option festlegen, indem Sie die CSPROJ-Datei bearbeiten und innerhalb des `PropertyGroup`-Abschnitts ein Element `StartupObject` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fccd8-119">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="fccd8-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fccd8-120">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="fccd8-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fccd8-121">Example</span></span>

<span data-ttu-id="fccd8-122">Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="fccd8-122">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="fccd8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fccd8-123">See also</span></span>

- [<span data-ttu-id="fccd8-124">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="fccd8-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="fccd8-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="fccd8-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
