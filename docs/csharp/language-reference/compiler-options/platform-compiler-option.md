---
title: -platform (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /platform
dev_langs:
- CSharp
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 44d4cadbc45eb141ecb7a83345d2a7a834ce5299
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="platform-c-compiler-options"></a><span data-ttu-id="34519-102">/platform (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="34519-102">/platform (C# Compiler Options)</span></span>
<span data-ttu-id="34519-103">Gibt an, welche Version der common Language Runtime (CLR) die Assembly ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="34519-103">Specifies which version of the common language runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34519-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34519-104">Syntax</span></span>  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34519-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34519-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="34519-106">anycpu (Standard), anycpu32bitpreferred, ARM, x64, x86, oder Itanium.</span><span class="sxs-lookup"><span data-stu-id="34519-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34519-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34519-107">Remarks</span></span>  
  
-   <span data-ttu-id="34519-108">**anycpu** (Standard) kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="34519-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="34519-109">Ihre Anwendung wird nach Möglichkeit als 64-Bit-Prozess ausgeführt und wechselt zurück zu 32-Bit, wenn nur dieser Modus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34519-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="34519-110">**anycpu32bitpreferred** kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="34519-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="34519-111">Die Anwendung wird auf Systemen, die sowohl 64-Bit- als auch 32-Bit-Anwendungen unterstützen, im 32-Bit-Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34519-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="34519-112">Sie können diese Option nur für Projekte angeben, die auf .NET Framework 4.5 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="34519-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="34519-113">**ARM** kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).</span><span class="sxs-lookup"><span data-stu-id="34519-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="34519-114">**x64** kompiliert die Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34519-114">**x64** compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="34519-115">**x86** kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="34519-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible common language runtime.</span></span>  
  
-   <span data-ttu-id="34519-116">**Itanium** kompiliert die Assembly für die 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="34519-116">**Itanium** compiles your assembly to be run by the 64-bit common language runtime on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="34519-117">Auf einem 64-Bit-Windows-Betriebssystem:</span><span class="sxs-lookup"><span data-stu-id="34519-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="34519-118">Mit **/platform:x86** kompilierte Assemblys werden in der 32-Bit-CLR unter WOW64 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34519-118">Assemblies compiled with **/platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="34519-119">Eine mit **/platform:anycpu** kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34519-119">A DLL compiled with the **/platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="34519-120">Ausführbare Dateien, die mit **/platform:anycpu** kompiliert werden, werden in der 64-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34519-120">Executables that are compiled with the **/platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="34519-121">Ausführbare Dateien, die mit **/platform:anycpu32bitpreferred** kompiliert werden, werden in der 32-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34519-121">Executables compiled with **/platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="34519-122">Die Einstellung **anycpu32bitpreferred** gilt nur für ausführbare Dateien (.exe) und erfordert .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="34519-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="34519-123">Weitere Informationen zum Entwickeln einer Anwendung, die auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll, finden Sie unter [64-Bit-Anwendungen](https://msdn.microsoft.com/library/ms241064).</span><span class="sxs-lookup"><span data-stu-id="34519-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="34519-124">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="34519-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="34519-125">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="34519-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="34519-126">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="34519-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="34519-127">Ändern Sie die Eigenschaft **Zielplattform**, und aktivieren oder deaktivieren Sie für Projekte, die auf .NET Framework 4.5 ausgerichtet sind, das Kontrollkästchen **32-Bit bevorzugen**.</span><span class="sxs-lookup"><span data-stu-id="34519-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="34519-128">Hinweis: **/platform** ist in der Entwicklerumgebung in Visual C# Express nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34519-128">**Note /platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="34519-129">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="34519-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34519-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34519-130">Example</span></span>  
 <span data-ttu-id="34519-131">Das folgende Beispiel zeigt, wie Sie die Option **/platform** verwenden können, um anzugeben, dass die Anwendung von der 64-Bit-CLR auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34519-131">The following example shows how to use the **/platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="34519-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34519-132">See Also</span></span>  
 <span data-ttu-id="34519-133">[C#-Compileroptionen](index.md) </span><span class="sxs-lookup"><span data-stu-id="34519-133">[C# Compiler Options](index.md) </span></span>  
 [<span data-ttu-id="34519-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="34519-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

