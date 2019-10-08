---
title: -Platform (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: 21526484b8423f9b366da64307bc44f8fb061fe9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005293"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="03fd9-102">-Platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03fd9-102">-platform (Visual Basic)</span></span>
<span data-ttu-id="03fd9-103">Gibt an, welche Plattformversion der common Language Runtime (CLR) die Ausgabedatei ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="03fd9-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03fd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03fd9-104">Syntax</span></span>  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="03fd9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="03fd9-105">Arguments</span></span>  
  
|<span data-ttu-id="03fd9-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="03fd9-106">Term</span></span>|<span data-ttu-id="03fd9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="03fd9-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="03fd9-108">Kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="03fd9-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="03fd9-109">Kompiliert Ihre Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="03fd9-110">Kompiliert Ihre Assembly für die Ausführung durch den 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="03fd9-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="03fd9-111">Kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).</span><span class="sxs-lookup"><span data-stu-id="03fd9-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="03fd9-112">Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="03fd9-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="03fd9-113">Die Anwendung wird auf 32-Bit-Versionen von Windows als 32-Bit-Anwendung und auf 64-Bit-Versionen von Windows als 64-Bit-Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="03fd9-114">Diese Meldung ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="03fd9-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="03fd9-115">Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="03fd9-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="03fd9-116">Die Anwendung wird als 32-Bit-Anwendung auf 32-Bit- und 64-Bit-Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="03fd9-117">Dieses Flag gilt nur für ausführbare Dateien (. EXE) und erfordert .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="03fd9-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03fd9-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03fd9-118">Remarks</span></span>  
 <span data-ttu-id="03fd9-119">Verwenden Sie die `-platform`-Option, um den Typ des Zielprozessors für die Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03fd9-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="03fd9-120">Im Allgemeinen werden in Visual Basic geschriebene .NET Framework-Assemblys identisch ausgeführt, unabhängig von der Plattform.</span><span class="sxs-lookup"><span data-stu-id="03fd9-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="03fd9-121">Es gibt jedoch einige Fälle, die sich auf unterschiedlichen Plattformen unterschiedlich verhalten.</span><span class="sxs-lookup"><span data-stu-id="03fd9-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="03fd9-122">Diese allgemeinen Fälle sind:</span><span class="sxs-lookup"><span data-stu-id="03fd9-122">These common cases are:</span></span>  
  
- <span data-ttu-id="03fd9-123">Strukturen, die Member enthalten, deren Größe sich je nach Plattform ändert (z. B. jeder beliebige Zeigertyp).</span><span class="sxs-lookup"><span data-stu-id="03fd9-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
- <span data-ttu-id="03fd9-124">Zeigerarithmetik, die Größen von Konstanten einschließt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
- <span data-ttu-id="03fd9-125">Fehlerhafter Plattformaufruf oder COM-Deklarationen, die `Integer` statt <xref:System.IntPtr> für Handles verwenden.</span><span class="sxs-lookup"><span data-stu-id="03fd9-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
- <span data-ttu-id="03fd9-126">Umwandeln von <xref:System.IntPtr> zu `Integer`.</span><span class="sxs-lookup"><span data-stu-id="03fd9-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
- <span data-ttu-id="03fd9-127">Verwendet einen Plattformaufruf oder COM-Interop für Komponenten, die nicht auf allen Plattformen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="03fd9-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="03fd9-128">Die Option **-Platform** minimiert einige Probleme, wenn Sie wissen, dass Sie Annahmen über die Architektur gemacht haben, in der Ihr Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03fd9-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="03fd9-129">Dies gilt insbesondere in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="03fd9-129">Specifically:</span></span>  
  
- <span data-ttu-id="03fd9-130">Wenn Sie sich entscheiden, eine 64-Bit-Plattform anzuzielen und die Anwendung auf einem 32-Bit-Computer ausgeführt wird, wird die Fehlermeldung sehr viel früher angezeigt und ist mehr problemorientiert als eine Fehlermeldung, die auftritt, wenn dieser Switch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03fd9-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
- <span data-ttu-id="03fd9-131">Wenn Sie die `x86`-Flag in der Option festlegen und anschließend die Anwendung auf einem 64-Bit-Computer ausgeführt wird, wird die Anwendung im WOW-Subsystem statt nativ ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="03fd9-132">Auf einem 64-Bit-Windows-Betriebssystem:</span><span class="sxs-lookup"><span data-stu-id="03fd9-132">On a 64-bit Windows operating system:</span></span>  
  
- <span data-ttu-id="03fd9-133">Kompilierte Assemblys mit `-platform:x86` werden in der 32-Bit-CLR unter WOW64 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
- <span data-ttu-id="03fd9-134">Kompilierte ausführbare Dateien mit dem `-platform:anycpu` werden in der 64-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
- <span data-ttu-id="03fd9-135">Eine mit der `-platform:anycpu` kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
- <span data-ttu-id="03fd9-136">Ausführbare Dateien, die mit `-platform:anycpu32bitpreferred` kompiliert werden, werden in der 32-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03fd9-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="03fd9-137">Weitere Informationen zum Entwickeln einer Anwendung, die auf einer 64-Bit-Version von Windows ausgeführt wird, finden Sie unter [64-Bit-Anwendungen](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="03fd9-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="03fd9-138">So legen Sie-Platform in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="03fd9-138">To set -platform in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="03fd9-139">Wählen Sie in **Projektmappen-Explorer**das Projekt aus, öffnen Sie das Menü **Projekt** , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03fd9-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="03fd9-140">Aktivieren bzw. deaktivieren Sie auf der Registerkarte **Kompilieren** das Kontrollkästchen **32-Bit bevorzugen** , oder wählen Sie in der Liste **Ziel-CPU** einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="03fd9-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="03fd9-141">Weitere Informationen finden Sie unter [Seite "kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="03fd9-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03fd9-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03fd9-142">Example</span></span>  
 <span data-ttu-id="03fd9-143">Das folgende Beispiel veranschaulicht, wie die `-platform`-Compileroption genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="03fd9-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="03fd9-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03fd9-144">See also</span></span>

- [<span data-ttu-id="03fd9-145">/Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03fd9-145">/target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="03fd9-146">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="03fd9-146">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="03fd9-147">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="03fd9-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
