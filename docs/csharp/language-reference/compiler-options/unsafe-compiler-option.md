---
title: -unsafe (C#-Compileroptionen)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4a8f7d099b2cd3c1b4331c87f853b617fef505ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726532"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="df64f-102">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="df64f-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="df64f-103">Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="df64f-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df64f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df64f-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="df64f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df64f-105">Remarks</span></span>  
 <span data-ttu-id="df64f-106">Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="df64f-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="df64f-107">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="df64f-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="df64f-108">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="df64f-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="df64f-109">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="df64f-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="df64f-110">Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="df64f-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="df64f-111">So fügen Sie diese Option in eine CSPROJ-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="df64f-111">To add this option in a csproj file</span></span>

<span data-ttu-id="df64f-112">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie die folgenden Elemente hinzu:</span><span class="sxs-lookup"><span data-stu-id="df64f-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="df64f-113">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="df64f-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df64f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df64f-114">Example</span></span>  
 <span data-ttu-id="df64f-115">Kompilieren Sie `in.cs` für den unsicheren Modus:</span><span class="sxs-lookup"><span data-stu-id="df64f-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="df64f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df64f-116">See also</span></span>

- [<span data-ttu-id="df64f-117">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="df64f-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="df64f-118">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="df64f-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
