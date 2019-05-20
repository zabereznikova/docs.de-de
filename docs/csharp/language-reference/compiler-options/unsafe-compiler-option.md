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
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877995"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="cda04-102">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="cda04-102">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="cda04-103">Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../keywords/unsafe.md)-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="cda04-103">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cda04-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="cda04-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="cda04-105">Remarks</span></span>

<span data-ttu-id="cda04-106">Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="cda04-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cda04-107">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="cda04-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="cda04-108">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="cda04-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="cda04-109">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="cda04-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="cda04-110">Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="cda04-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="cda04-111">So fügen Sie diese Option in eine CSPROJ-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="cda04-111">To add this option in a csproj file</span></span>

<span data-ttu-id="cda04-112">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie die folgenden Elemente hinzu:</span><span class="sxs-lookup"><span data-stu-id="cda04-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="cda04-113">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="cda04-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda04-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cda04-114">Example</span></span>

<span data-ttu-id="cda04-115">Kompilieren Sie `in.cs` für den unsicheren Modus:</span><span class="sxs-lookup"><span data-stu-id="cda04-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cda04-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda04-116">See also</span></span>

- [<span data-ttu-id="cda04-117">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="cda04-117">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="cda04-118">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="cda04-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
