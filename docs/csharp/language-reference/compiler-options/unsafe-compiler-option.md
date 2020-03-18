---
title: -unsafe (C#-Compileroptionen)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 146299fda103567b111c66400c17edf36addd843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "65877995"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="914c4-102">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="914c4-102">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="914c4-103">Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../keywords/unsafe.md)-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="914c4-103">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="914c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="914c4-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="914c4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="914c4-105">Remarks</span></span>

<span data-ttu-id="914c4-106">Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="914c4-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="914c4-107">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="914c4-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="914c4-108">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="914c4-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="914c4-109">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="914c4-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="914c4-110">Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="914c4-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="914c4-111">So fügen Sie diese Option in eine CSPROJ-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="914c4-111">To add this option in a csproj file</span></span>

<span data-ttu-id="914c4-112">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie die folgenden Elemente hinzu:</span><span class="sxs-lookup"><span data-stu-id="914c4-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="914c4-113">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="914c4-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="914c4-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="914c4-114">Example</span></span>

<span data-ttu-id="914c4-115">Kompilieren Sie `in.cs` für den unsicheren Modus:</span><span class="sxs-lookup"><span data-stu-id="914c4-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="914c4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="914c4-116">See also</span></span>

- [<span data-ttu-id="914c4-117">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="914c4-117">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="914c4-118">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="914c4-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
