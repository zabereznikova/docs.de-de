---
title: /platform (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d52ade26bc249625a77720fe05ad9c1ab58b04f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="platform-visual-basic"></a><span data-ttu-id="d08a1-102">/platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d08a1-102">/platform (Visual Basic)</span></span>
<span data-ttu-id="d08a1-103">Gibt an, welche Plattformversion der common Language Runtime (CLR) die Ausgabedatei ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="d08a1-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d08a1-104">Syntax</span></span>  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="d08a1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d08a1-105">Arguments</span></span>  
  
|<span data-ttu-id="d08a1-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d08a1-106">Term</span></span>|<span data-ttu-id="d08a1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d08a1-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="d08a1-108">Kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="d08a1-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="d08a1-109">Kompiliert Ihre Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="d08a1-110">Kompiliert Ihre Assembly für die Ausführung durch den 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="d08a1-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="d08a1-111">Kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).</span><span class="sxs-lookup"><span data-stu-id="d08a1-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="d08a1-112">Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="d08a1-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="d08a1-113">Die Anwendung wird auf 32-Bit-Versionen von Windows als 32-Bit-Anwendung und auf 64-Bit-Versionen von Windows als 64-Bit-Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="d08a1-114">Diese Meldung ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d08a1-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="d08a1-115">Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform.</span><span class="sxs-lookup"><span data-stu-id="d08a1-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="d08a1-116">Die Anwendung wird als 32-Bit-Anwendung auf 32-Bit- und 64-Bit-Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="d08a1-117">Dieses Flag ist nur gültig für ausführbare Dateien (.(EXE) und erfordert [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d08a1-117">This flag is valid only for executables (.EXE) and requires [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d08a1-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d08a1-118">Remarks</span></span>  
 <span data-ttu-id="d08a1-119">Verwenden Sie die `/platform`-Option, um den Typ des Zielprozessors für die Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d08a1-119">Use the `/platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="d08a1-120">Im Allgemeinen werden in Visual Basic geschriebene .NET Framework-Assemblys identisch ausgeführt, unabhängig von der Plattform.</span><span class="sxs-lookup"><span data-stu-id="d08a1-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="d08a1-121">Es gibt jedoch einige Fälle, die sich auf unterschiedlichen Plattformen unterschiedlich verhalten.</span><span class="sxs-lookup"><span data-stu-id="d08a1-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="d08a1-122">Diese allgemeinen Fälle sind:</span><span class="sxs-lookup"><span data-stu-id="d08a1-122">These common cases are:</span></span>  
  
-   <span data-ttu-id="d08a1-123">Strukturen, die Member enthalten, deren Größe sich je nach Plattform ändert (z. B. jeder beliebige Zeigertyp).</span><span class="sxs-lookup"><span data-stu-id="d08a1-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
-   <span data-ttu-id="d08a1-124">Zeigerarithmetik, die Größen von Konstanten einschließt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="d08a1-125">Fehlerhafter Plattformaufruf oder COM-Deklarationen, die `Integer` statt <xref:System.IntPtr> für Handles verwenden.</span><span class="sxs-lookup"><span data-stu-id="d08a1-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
-   <span data-ttu-id="d08a1-126">Umwandeln von <xref:System.IntPtr> zu `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d08a1-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
-   <span data-ttu-id="d08a1-127">Verwendet einen Plattformaufruf oder COM-Interop für Komponenten, die nicht auf allen Plattformen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d08a1-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="d08a1-128">Die **/Platform** -Option löst einige Probleme, wenn Sie kennen Sie Annahmen über die Architektur der Code ausgeführt wird, auf vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="d08a1-128">The **/platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="d08a1-129">Dies gilt insbesondere in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="d08a1-129">Specifically:</span></span>  
  
-   <span data-ttu-id="d08a1-130">Wenn Sie sich entscheiden, eine 64-Bit-Plattform anzuzielen und die Anwendung auf einem 32-Bit-Computer ausgeführt wird, wird die Fehlermeldung sehr viel früher angezeigt und ist mehr problemorientiert als eine Fehlermeldung, die auftritt, wenn dieser Switch nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d08a1-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
-   <span data-ttu-id="d08a1-131">Wenn Sie die `x86`-Flag in der Option festlegen und anschließend die Anwendung auf einem 64-Bit-Computer ausgeführt wird, wird die Anwendung im WOW-Subsystem statt nativ ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="d08a1-132">Auf einem 64-Bit-Windows-Betriebssystem:</span><span class="sxs-lookup"><span data-stu-id="d08a1-132">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="d08a1-133">Kompilierte Assemblys mit `/platform:x86` werden in der 32-Bit-CLR unter WOW64 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-133">Assemblies compiled with `/platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="d08a1-134">Kompilierte ausführbare Dateien mit dem `/platform:anycpu` werden in der 64-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-134">Executables compiled with the `/platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="d08a1-135">Eine mit der `/platform:anycpu` kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-135">A DLL compiled with the `/platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
-   <span data-ttu-id="d08a1-136">Ausführbare Dateien, die mit `/platform:anycpu32bitpreferred` kompiliert werden, werden in der 32-Bit-CLR ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d08a1-136">Executables that are compiled with `/platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="d08a1-137">Weitere Informationen zur Entwicklung einer Anwendung auf einer 64-Bit-Version von Windows ausführen, finden Sie unter [64-Bit-Anwendungen](https://msdn.microsoft.com/library/ms241064).</span><span class="sxs-lookup"><span data-stu-id="d08a1-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-platform-in-the-visual-studio-ide"></a><span data-ttu-id="d08a1-138">Festlegen der / Platform in Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="d08a1-138">To set /platform in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="d08a1-139">In **Projektmappen-Explorer**, wählen Sie das Projekt, öffnen Sie die **Projekt** Menü, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d08a1-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="d08a1-140">Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="d08a1-140">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="d08a1-141">Auf der **Kompilieren** Registerkarte aktivieren oder Deaktivieren der **32-Bit bevorzugen** Kontrollkästchen, oder in der **Ziel-CPU** wählen Sie einen Wert.</span><span class="sxs-lookup"><span data-stu-id="d08a1-141">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="d08a1-142">Weitere Informationen finden Sie unter [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d08a1-142">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d08a1-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d08a1-143">Example</span></span>  
 <span data-ttu-id="d08a1-144">Das folgende Beispiel veranschaulicht, wie die `/platform`-Compileroption genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="d08a1-144">The following example illustrates how to use the `/platform` compiler option.</span></span>  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d08a1-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d08a1-145">See Also</span></span>  
 [<span data-ttu-id="d08a1-146">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d08a1-146">/target (Visual Basic)</span></span>](target.md)  
 [<span data-ttu-id="d08a1-147">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d08a1-147">Visual Basic Command-Line Compiler</span></span>](index.md)  
 [<span data-ttu-id="d08a1-148">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d08a1-148">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
