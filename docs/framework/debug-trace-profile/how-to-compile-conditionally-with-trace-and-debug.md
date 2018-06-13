---
title: 'Gewusst wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen'
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45e62fed53999636e23693ad7e61fedf21bc5423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390574"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="86d9b-102">Gewusst wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-102">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="86d9b-103">Beim Debuggen einer Anwendung während der Entwicklung wird sowohl die Ablaufverfolgungsausgabe als auch die Debugausgabe im Ausgabefenster von Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86d9b-103">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="86d9b-104">Allerdings müssen Sie Ihre instrumentierten Anwendungen mit aktivierter **TRACE**-Compilerdirektive kompilieren, um Ablaufverfolgungsfunktionen in eine bereitgestellte Anwendung aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-104">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="86d9b-105">Dadurch kann der Ablaufverfolgungscode in die Releaseversion der Anwendung kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="86d9b-105">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="86d9b-106">Wenn Sie die **TRACE**-Anweisung nicht aktivieren, wird der gesamte Ablaufverfolgungscode bei der Kompilierung ignoriert und nicht in den ausführbaren Code aufgenommen, den Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-106">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="86d9b-107">Sowohl die Ablaufverfolgungsmethoden als auch die Debugmethoden weisen zugeordnete Conditional-Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="86d9b-107">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="86d9b-108">Wenn das Conditional-Attribut für die Ablaufverfolgung beispielsweise **TRUE** ist, werden alle Ablaufverfolgungsanweisungen in eine Assembly (eine kompilierte EXE- oder DLL-Datei) aufgenommen. Ist das Conditional-Attribut **TRACE** hingegen **FALSE**, werden die Ablaufverfolgungsanweisungen nicht aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-108">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="86d9b-109">Für einen Build kann das Conditional-Attribut **Trace** oder **Debug** aktiviert sein oder beide Conditional-Attribute oder keines von beiden.</span><span class="sxs-lookup"><span data-stu-id="86d9b-109">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="86d9b-110">Daher gibt es vier Typen von Builds: **Debug**, **Trace**, beide oder keines von beiden.</span><span class="sxs-lookup"><span data-stu-id="86d9b-110">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="86d9b-111">Manche Releasebuilds für die Produktionsbereitstellung enthalten keines von beiden, und die meisten Debugbuilds enthalten beide.</span><span class="sxs-lookup"><span data-stu-id="86d9b-111">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="86d9b-112">Sie können die Compilereinstellungen für die Anwendung auf verschiedene Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="86d9b-112">You can specify the compiler settings for your application in several ways:</span></span>  
  
-   <span data-ttu-id="86d9b-113">Eigenschaftenseiten</span><span class="sxs-lookup"><span data-stu-id="86d9b-113">The property pages</span></span>  
  
-   <span data-ttu-id="86d9b-114">Die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="86d9b-114">The command line</span></span>  
  
-   <span data-ttu-id="86d9b-115">**#CONST** (für Visual Basic) und **#define** (für C#)</span><span class="sxs-lookup"><span data-stu-id="86d9b-115">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="86d9b-116">So ändern Sie die Kompilierungseinstellungen im Dialogfeld "Eigenschaftenseiten"</span><span class="sxs-lookup"><span data-stu-id="86d9b-116">To change compile settings from the property pages dialog box</span></span>  
  
1.  <span data-ttu-id="86d9b-117">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten.</span><span class="sxs-lookup"><span data-stu-id="86d9b-117">Right-click the project node in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="86d9b-118">Wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="86d9b-118">Choose **Properties** from the shortcut menu.</span></span>  
  
    -   <span data-ttu-id="86d9b-119">Klicken Sie in Visual Basic im linken Bereich der Eigenschaftenseite auf die Registerkarte **Kompilieren**, und klicken Sie dann auf die Schaltfläche **Erweiterte Kompilierungsoptionen**, um das Dialogfeld **Erweiterte Kompilierungsoptionen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-119">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="86d9b-120">Aktivieren Sie die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-120">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="86d9b-121">Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-121">Clear the check boxes for settings you want to disable.</span></span>  
  
    -   <span data-ttu-id="86d9b-122">Klicken Sie in C# auf die Registerkarte **Erstellen** im linken Bereich der Eigenschaftenseite, und aktivieren Sie dann die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-122">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="86d9b-123">Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-123">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="86d9b-124">So kompilieren Sie instrumentierten Code über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="86d9b-124">To compile instrumented code using the command line</span></span>  
  
1.  <span data-ttu-id="86d9b-125">Legen Sie über die Befehlszeile einen bedingten Compilerschalter fest.</span><span class="sxs-lookup"><span data-stu-id="86d9b-125">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="86d9b-126">Der Compiler integriert Ablaufverfolgungs- oder Debugcode in die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="86d9b-126">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="86d9b-127">Beispielsweise wird der Ablaufverfolgungscode in eine kompilierte ausführbare Datei aufgenommen, wenn die folgende Compileranweisung über die Befehlszeile eingegeben wird:</span><span class="sxs-lookup"><span data-stu-id="86d9b-127">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="86d9b-128">Für Visual Basic: **Vbc-r:System.dll -d: TRACE = "true" -d: DEBUG = FALSE MyApplication.vb**</span><span class="sxs-lookup"><span data-stu-id="86d9b-128">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="86d9b-129">Für c#: **csc-r:System.dll -d: TRACE -d: DEBUG = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="86d9b-129">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="86d9b-130">Lassen Sie einen Leerraum zwischen den Dateinamen, um mehr als eine Anwendungsdatei zu kompilieren, z.B. **MyApplication1.vb MyApplication2.vb MyApplication3.vb** oder **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span><span class="sxs-lookup"><span data-stu-id="86d9b-130">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="86d9b-131">Die in den obigen Beispielen verwendeten Anweisungen zur bedingten Kompilierung bedeuten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="86d9b-131">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="86d9b-132">Direktive</span><span class="sxs-lookup"><span data-stu-id="86d9b-132">Directive</span></span>|<span data-ttu-id="86d9b-133">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="86d9b-133">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="86d9b-134">Visual Basic-Compiler</span><span class="sxs-lookup"><span data-stu-id="86d9b-134">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="86d9b-135">C#-Compiler</span><span class="sxs-lookup"><span data-stu-id="86d9b-135">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="86d9b-136">Verweist auf eine externe Assembly (EXE oder DLL)</span><span class="sxs-lookup"><span data-stu-id="86d9b-136">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="86d9b-137">Definiert ein Symbol für bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="86d9b-137">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="86d9b-138">Sie müssen TRACE oder DEBUG mit Großbuchstaben schreiben.</span><span class="sxs-lookup"><span data-stu-id="86d9b-138">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="86d9b-139">Geben Sie an der Eingabeaufforderung `vbc /?` (für Visual Basic) oder `csc /?` (für C#) ein, um weitere Informationen zu den Befehlen zur bedingten Kompilierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="86d9b-139">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="86d9b-140">Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) oder [Aufrufen des Befehlszeilencompilers](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="86d9b-140">For more information, see [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="86d9b-141">So führen Sie die bedingte Kompilierung mit #CONST oder #define durch</span><span class="sxs-lookup"><span data-stu-id="86d9b-141">To perform conditional compilation using #CONST or #define</span></span>  
  
1.  <span data-ttu-id="86d9b-142">Geben Sie am Anfang der Quellcodedatei die entsprechende Anweisung für Ihre Programmiersprache ein.</span><span class="sxs-lookup"><span data-stu-id="86d9b-142">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="86d9b-143">Sprache</span><span class="sxs-lookup"><span data-stu-id="86d9b-143">Language</span></span>|<span data-ttu-id="86d9b-144">Anweisung</span><span class="sxs-lookup"><span data-stu-id="86d9b-144">Statement</span></span>|<span data-ttu-id="86d9b-145">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="86d9b-145">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="86d9b-146">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="86d9b-146">**Visual Basic**</span></span>|<span data-ttu-id="86d9b-147">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="86d9b-147">**#CONST TRACE = true**</span></span>|<span data-ttu-id="86d9b-148">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="86d9b-148">Enables tracing</span></span>|  
    ||<span data-ttu-id="86d9b-149">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="86d9b-149">**#CONST TRACE = false**</span></span>|<span data-ttu-id="86d9b-150">Deaktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="86d9b-150">Disables tracing</span></span>|  
    ||<span data-ttu-id="86d9b-151">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="86d9b-151">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="86d9b-152">Aktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-152">Enables debugging</span></span>|  
    ||<span data-ttu-id="86d9b-153">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="86d9b-153">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="86d9b-154">Deaktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-154">Disables debugging</span></span>|  
    |<span data-ttu-id="86d9b-155">**C#**</span><span class="sxs-lookup"><span data-stu-id="86d9b-155">**C#**</span></span>|<span data-ttu-id="86d9b-156">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="86d9b-156">**#define TRACE**</span></span>|<span data-ttu-id="86d9b-157">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="86d9b-157">Enables tracing</span></span>|  
    ||<span data-ttu-id="86d9b-158">**#undefine TRACE**</span><span class="sxs-lookup"><span data-stu-id="86d9b-158">**#undef TRACE**</span></span>|<span data-ttu-id="86d9b-159">Deaktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="86d9b-159">Disables tracing</span></span>|  
    ||<span data-ttu-id="86d9b-160">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="86d9b-160">**#define DEBUG**</span></span>|<span data-ttu-id="86d9b-161">Aktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-161">Enables debugging</span></span>|  
    ||<span data-ttu-id="86d9b-162">**#undefine DEBUG**</span><span class="sxs-lookup"><span data-stu-id="86d9b-162">**#undef DEBUG**</span></span>|<span data-ttu-id="86d9b-163">Deaktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-163">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="86d9b-164">So deaktivieren Sie die Ablaufverfolgung oder das Debuggen</span><span class="sxs-lookup"><span data-stu-id="86d9b-164">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="86d9b-165">Löschen Sie die Compileranweisung aus dem Quellcode.</span><span class="sxs-lookup"><span data-stu-id="86d9b-165">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="86d9b-166">\- oder –</span><span class="sxs-lookup"><span data-stu-id="86d9b-166">\- or -</span></span>  
  
<span data-ttu-id="86d9b-167">Kommentieren Sie die Compileranweisung aus.</span><span class="sxs-lookup"><span data-stu-id="86d9b-167">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86d9b-168">Wenn Sie kompilieren möchten, können Sie entweder **Erstellen** aus dem Menü **Erstellen** auswählen oder die Befehlszeilenmethode verwenden, allerdings ohne Eingabe von **d:** zum Definieren der Symbole für bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="86d9b-168">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d9b-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86d9b-169">See Also</span></span>  
 [<span data-ttu-id="86d9b-170">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="86d9b-170">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [<span data-ttu-id="86d9b-171">Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="86d9b-171">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)  
 [<span data-ttu-id="86d9b-172">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="86d9b-172">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="86d9b-173">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="86d9b-173">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="86d9b-174">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="86d9b-174">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="86d9b-175">Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="86d9b-175">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 [<span data-ttu-id="86d9b-176">Gewusst wie: Aufrufen des Befehlszeilencompilers</span><span class="sxs-lookup"><span data-stu-id="86d9b-176">How to: Invoke the Command-Line Compiler</span></span>](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
