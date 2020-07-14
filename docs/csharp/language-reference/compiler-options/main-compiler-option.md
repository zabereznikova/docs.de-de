---
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 1de3d51953b632e3881db76202b63d3f287b39fe
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051869"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="1e064-102">-main (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="1e064-102">-main (C# Compiler Options)</span></span>

<span data-ttu-id="1e064-103">Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="1e064-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e064-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e064-104">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="1e064-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1e064-105">Arguments</span></span>
 `class`  
 <span data-ttu-id="1e064-106">Der Typ, der die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="1e064-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="1e064-107">Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e064-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="1e064-108">Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.</span><span class="sxs-lookup"><span data-stu-id="1e064-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e064-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e064-109">Remarks</span></span>

<span data-ttu-id="1e064-110">Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1e064-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="1e064-111">Diese Option wird verwendet, wenn eine *EXE*-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="1e064-111">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1e064-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="1e064-112">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="1e064-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="1e064-113">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="1e064-114">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="1e064-114">Click the **Application** property page.</span></span>

3. <span data-ttu-id="1e064-115">Ändern Sie die Eigenschaft **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="1e064-115">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="1e064-116">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e064-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="1e064-117">So legen Sie diese Compileroption fest, indem Sie die *CSPROJ*-Datei manuell bearbeiten</span><span class="sxs-lookup"><span data-stu-id="1e064-117">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="1e064-118">Sie können diese Option festlegen, indem Sie die CSPROJ-Datei bearbeiten und innerhalb des `PropertyGroup`-Abschnitts ein Element `StartupObject` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e064-118">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="1e064-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e064-119">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="1e064-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e064-120">Example</span></span>

<span data-ttu-id="1e064-121">Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="1e064-121">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="1e064-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e064-122">See also</span></span>

- [<span data-ttu-id="1e064-123">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="1e064-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1e064-124">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e064-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
