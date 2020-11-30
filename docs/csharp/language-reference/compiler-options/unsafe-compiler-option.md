---
description: -unsafe (C#-Compileroptionen)
title: -unsafe (C#-Compileroptionen)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 0f6d94dd25a020d96430746c4b5e7aefd0f679da
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89140840"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="507ef-103">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="507ef-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="507ef-104">Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../keywords/unsafe.md)-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="507ef-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="507ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="507ef-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="507ef-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="507ef-106">Remarks</span></span>

<span data-ttu-id="507ef-107">Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="507ef-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="507ef-108">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="507ef-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="507ef-109">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="507ef-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="507ef-110">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="507ef-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="507ef-111">Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="507ef-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="507ef-112">So fügen Sie diese Option in eine CSPROJ-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="507ef-112">To add this option in a csproj file</span></span>

<span data-ttu-id="507ef-113">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie die folgenden Elemente hinzu:</span><span class="sxs-lookup"><span data-stu-id="507ef-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="507ef-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="507ef-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="507ef-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="507ef-115">Example</span></span>

<span data-ttu-id="507ef-116">Kompilieren Sie `in.cs` für den unsicheren Modus:</span><span class="sxs-lookup"><span data-stu-id="507ef-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="507ef-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="507ef-117">See also</span></span>

- [<span data-ttu-id="507ef-118">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="507ef-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="507ef-119">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="507ef-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
