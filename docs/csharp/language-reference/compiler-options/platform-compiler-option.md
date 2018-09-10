---
title: -platform (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: f52192087eb7b73ee930eea073e0c5716ad8c636
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507591"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="7f710-102">-platform (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7f710-102">-platform (C# Compiler Options)</span></span>
<span data-ttu-id="7f710-103">Gibt an, welche Version der Common Language Runtime (CLR) die Assembly ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="7f710-103">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f710-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-104">Syntax</span></span>  
  
```console  
-platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f710-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f710-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="7f710-106">anycpu (Standard), anycpu32bitpreferred, ARM, x64, x86, oder Itanium.</span><span class="sxs-lookup"><span data-stu-id="7f710-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f710-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f710-107">Remarks</span></span>  
  
-   <span data-ttu-id="7f710-108">**anycpu** (Standard) kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="7f710-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="7f710-109">Ihre Anwendung wird nach Möglichkeit als 64-Bit-Prozess ausgeführt und wechselt zurück zu 32-Bit, wenn nur dieser Modus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7f710-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="7f710-110">**anycpu32bitpreferred** kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="7f710-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="7f710-111">Die Anwendung wird auf Systemen, die sowohl 64-Bit- als auch 32-Bit-Anwendungen unterstützen, im 32-Bit-Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="7f710-112">Sie können diese Option nur für Projekte angeben, die auf .NET Framework 4.5 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="7f710-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="7f710-113">**ARM** kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).</span><span class="sxs-lookup"><span data-stu-id="7f710-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="7f710-114">**x64** kompiliert Ihre Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Befehlssatz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f710-114">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="7f710-115">**x86** kompiliert die Assembly für die 32-Bit-CLR (Common Language Runtime), die mit x86 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7f710-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>  
  
-   <span data-ttu-id="7f710-116">**Itanium** kompiliert Ihre Assembly für die Ausführung durch die 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="7f710-116">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="7f710-117">Auf einem 64-Bit-Windows-Betriebssystem:</span><span class="sxs-lookup"><span data-stu-id="7f710-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="7f710-118">Mit **-platform:x86** kompilierte Assemblys werden in der 32-Bit-CLR unter WOW64 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-118">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="7f710-119">Eine mit **-platform:anycpu** kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-119">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="7f710-120">Ausführbare Dateien, die mit **-platform:anycpu** kompiliert werden, werden in der 64-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-120">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="7f710-121">Ausführbare Dateien, die mit **-platform:anycpu32bitpreferred** kompiliert werden, werden in der 32-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-121">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="7f710-122">Die Einstellung **anycpu32bitpreferred** gilt nur für ausführbare Dateien (.exe) und erfordert .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7f710-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="7f710-123">Weitere Informationen zum Entwickeln einer Anwendung, die auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll, finden Sie unter [64-Bit-Anwendungen](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="7f710-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7f710-124">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="7f710-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="7f710-125">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="7f710-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="7f710-126">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="7f710-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="7f710-127">Ändern Sie die Eigenschaft **Zielplattform**, und aktivieren oder deaktivieren Sie für Projekte, die auf .NET Framework 4.5 ausgerichtet sind, das Kontrollkästchen **32-Bit bevorzugen**.</span><span class="sxs-lookup"><span data-stu-id="7f710-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="7f710-128">Hinweis: **-platform** ist in der Entwicklerumgebung in Visual C# Express nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7f710-128">**Note -platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="7f710-129">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f710-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f710-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f710-130">Example</span></span>  
 <span data-ttu-id="7f710-131">Das folgende Beispiel zeigt, wie Sie die Option **-platform** verwenden können, um anzugeben, dass die Anwendung von der 64-Bit-CLR auf einem 64-Bit-Windows-Betriebssystem ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f710-131">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc -platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f710-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f710-132">See Also</span></span>  

- [<span data-ttu-id="7f710-133">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7f710-133">C# Compiler Options</span></span>](index.md)  
- [<span data-ttu-id="7f710-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7f710-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
