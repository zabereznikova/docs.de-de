---
title: 'Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen'
description: Erfahren Sie, wie Sie bedingt mit den bedingten Attributen für Ablauf Verfolgung und Debuggen kompilieren, wenn Sie eine .NET-Anwendung
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
ms.openlocfilehash: 8758b793866ec0317f91d636476d33bd001ddd78
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051219"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="c50f3-103">Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-103">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="c50f3-104">Beim Debuggen einer Anwendung während der Entwicklung wird sowohl die Ablaufverfolgungsausgabe als auch die Debugausgabe im Ausgabefenster von Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c50f3-104">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="c50f3-105">Allerdings müssen Sie Ihre instrumentierten Anwendungen mit aktivierter **TRACE**-Compilerdirektive kompilieren, um Ablaufverfolgungsfunktionen in eine bereitgestellte Anwendung aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-105">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="c50f3-106">Dadurch kann der Ablaufverfolgungscode in die Releaseversion der Anwendung kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c50f3-106">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="c50f3-107">Wenn Sie die **TRACE**-Anweisung nicht aktivieren, wird der gesamte Ablaufverfolgungscode bei der Kompilierung ignoriert und nicht in den ausführbaren Code aufgenommen, den Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-107">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="c50f3-108">Sowohl die Ablaufverfolgungsmethoden als auch die Debugmethoden weisen zugeordnete Conditional-Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="c50f3-108">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="c50f3-109">Wenn das Conditional-Attribut für die Ablaufverfolgung beispielsweise **TRUE** ist, werden alle Ablaufverfolgungsanweisungen in eine Assembly (eine kompilierte EXE- oder DLL-Datei) aufgenommen. Ist das Conditional-Attribut **TRACE** hingegen **FALSE**, werden die Ablaufverfolgungsanweisungen nicht aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-109">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="c50f3-110">Für einen Build kann das Conditional-Attribut **Trace** oder **Debug** aktiviert sein oder beide Conditional-Attribute oder keines von beiden.</span><span class="sxs-lookup"><span data-stu-id="c50f3-110">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="c50f3-111">Daher gibt es vier Typen von Builds: **Debug**, **Trace**, beide oder keines von beiden.</span><span class="sxs-lookup"><span data-stu-id="c50f3-111">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="c50f3-112">Manche Releasebuilds für die Produktionsbereitstellung enthalten keines von beiden, und die meisten Debugbuilds enthalten beide.</span><span class="sxs-lookup"><span data-stu-id="c50f3-112">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="c50f3-113">Sie können die Compilereinstellungen für die Anwendung auf verschiedene Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="c50f3-113">You can specify the compiler settings for your application in several ways:</span></span>  
  
- <span data-ttu-id="c50f3-114">Eigenschaftenseiten</span><span class="sxs-lookup"><span data-stu-id="c50f3-114">The property pages</span></span>  
  
- <span data-ttu-id="c50f3-115">Die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c50f3-115">The command line</span></span>  
  
- <span data-ttu-id="c50f3-116">**#CONST** (für Visual Basic) und **#define** (für C#)</span><span class="sxs-lookup"><span data-stu-id="c50f3-116">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="c50f3-117">So ändern Sie die Kompilierungseinstellungen im Dialogfeld "Eigenschaftenseiten"</span><span class="sxs-lookup"><span data-stu-id="c50f3-117">To change compile settings from the property pages dialog box</span></span>  
  
1. <span data-ttu-id="c50f3-118">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten.</span><span class="sxs-lookup"><span data-stu-id="c50f3-118">Right-click the project node in **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="c50f3-119">Wählen Sie im Kontextmenü den Befehl **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="c50f3-119">Choose **Properties** from the shortcut menu.</span></span>  
  
    - <span data-ttu-id="c50f3-120">Klicken Sie in Visual Basic im linken Bereich der Eigenschaftenseite auf die Registerkarte **Kompilieren**, und klicken Sie dann auf die Schaltfläche **Erweiterte Kompilierungsoptionen**, um das Dialogfeld **Erweiterte Kompilierungsoptionen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-120">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="c50f3-121">Aktivieren Sie die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-121">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="c50f3-122">Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-122">Clear the check boxes for settings you want to disable.</span></span>  
  
    - <span data-ttu-id="c50f3-123">Klicken Sie in C# auf die Registerkarte **Erstellen** im linken Bereich der Eigenschaftenseite, und aktivieren Sie dann die Kontrollkästchen für die Compilereinstellungen, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-123">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="c50f3-124">Deaktivieren Sie die Kontrollkästchen für die Einstellungen, die deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-124">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="c50f3-125">So kompilieren Sie instrumentierten Code über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c50f3-125">To compile instrumented code using the command line</span></span>  
  
1. <span data-ttu-id="c50f3-126">Legen Sie über die Befehlszeile einen bedingten Compilerschalter fest.</span><span class="sxs-lookup"><span data-stu-id="c50f3-126">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="c50f3-127">Der Compiler integriert Ablaufverfolgungs- oder Debugcode in die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="c50f3-127">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="c50f3-128">Beispielsweise wird der Ablaufverfolgungscode in eine kompilierte ausführbare Datei aufgenommen, wenn die folgende Compileranweisung über die Befehlszeile eingegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c50f3-128">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="c50f3-129">Für Visual Basic: **vbc -r:System.dll-d:Trace = true-d:Debug = FALSE MyApplication. vb**</span><span class="sxs-lookup"><span data-stu-id="c50f3-129">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="c50f3-130">Für c#: **csc -r:System.dll-d:Trace-d:Debug = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="c50f3-130">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="c50f3-131">Lassen Sie einen Leerraum zwischen den Dateinamen, um mehr als eine Anwendungsdatei zu kompilieren, z.B. **MyApplication1.vb MyApplication2.vb MyApplication3.vb** oder **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span><span class="sxs-lookup"><span data-stu-id="c50f3-131">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="c50f3-132">Die in den obigen Beispielen verwendeten Anweisungen zur bedingten Kompilierung bedeuten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c50f3-132">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="c50f3-133">Anweisung</span><span class="sxs-lookup"><span data-stu-id="c50f3-133">Directive</span></span>|<span data-ttu-id="c50f3-134">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="c50f3-134">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="c50f3-135">Visual Basic-Compiler</span><span class="sxs-lookup"><span data-stu-id="c50f3-135">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="c50f3-136">C#-Compiler</span><span class="sxs-lookup"><span data-stu-id="c50f3-136">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="c50f3-137">Verweist auf eine externe Assembly (EXE oder DLL)</span><span class="sxs-lookup"><span data-stu-id="c50f3-137">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="c50f3-138">Definiert ein Symbol für bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="c50f3-138">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="c50f3-139">Sie müssen TRACE oder DEBUG mit Großbuchstaben schreiben.</span><span class="sxs-lookup"><span data-stu-id="c50f3-139">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="c50f3-140">Geben Sie an der Eingabeaufforderung `vbc /?` (für Visual Basic) oder `csc /?` (für C#) ein, um weitere Informationen zu den Befehlen zur bedingten Kompilierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c50f3-140">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="c50f3-141">Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) oder [Aufrufen des Befehlszeilencompilers](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c50f3-141">For more information, see [Building from the Command Line](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="c50f3-142">So führen Sie die bedingte Kompilierung mit #CONST oder #define durch</span><span class="sxs-lookup"><span data-stu-id="c50f3-142">To perform conditional compilation using #CONST or #define</span></span>  
  
1. <span data-ttu-id="c50f3-143">Geben Sie am Anfang der Quellcodedatei die entsprechende Anweisung für Ihre Programmiersprache ein.</span><span class="sxs-lookup"><span data-stu-id="c50f3-143">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="c50f3-144">Sprache</span><span class="sxs-lookup"><span data-stu-id="c50f3-144">Language</span></span>|<span data-ttu-id="c50f3-145">-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c50f3-145">Statement</span></span>|<span data-ttu-id="c50f3-146">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="c50f3-146">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="c50f3-147">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="c50f3-147">**Visual Basic**</span></span>|<span data-ttu-id="c50f3-148">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="c50f3-148">**#CONST TRACE = true**</span></span>|<span data-ttu-id="c50f3-149">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c50f3-149">Enables tracing</span></span>|  
    ||<span data-ttu-id="c50f3-150">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="c50f3-150">**#CONST TRACE = false**</span></span>|<span data-ttu-id="c50f3-151">Deaktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c50f3-151">Disables tracing</span></span>|  
    ||<span data-ttu-id="c50f3-152">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="c50f3-152">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="c50f3-153">Aktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-153">Enables debugging</span></span>|  
    ||<span data-ttu-id="c50f3-154">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="c50f3-154">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="c50f3-155">Deaktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-155">Disables debugging</span></span>|  
    |<span data-ttu-id="c50f3-156">**C#**</span><span class="sxs-lookup"><span data-stu-id="c50f3-156">**C#**</span></span>|<span data-ttu-id="c50f3-157">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="c50f3-157">**#define TRACE**</span></span>|<span data-ttu-id="c50f3-158">Aktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c50f3-158">Enables tracing</span></span>|  
    ||<span data-ttu-id="c50f3-159">**#undefine TRACE**</span><span class="sxs-lookup"><span data-stu-id="c50f3-159">**#undef TRACE**</span></span>|<span data-ttu-id="c50f3-160">Deaktiviert die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c50f3-160">Disables tracing</span></span>|  
    ||<span data-ttu-id="c50f3-161">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="c50f3-161">**#define DEBUG**</span></span>|<span data-ttu-id="c50f3-162">Aktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-162">Enables debugging</span></span>|  
    ||<span data-ttu-id="c50f3-163">**#undefine DEBUG**</span><span class="sxs-lookup"><span data-stu-id="c50f3-163">**#undef DEBUG**</span></span>|<span data-ttu-id="c50f3-164">Deaktiviert das Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-164">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="c50f3-165">So deaktivieren Sie die Ablaufverfolgung oder das Debuggen</span><span class="sxs-lookup"><span data-stu-id="c50f3-165">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="c50f3-166">Löschen Sie die Compilerdirektive aus dem Quellcode.</span><span class="sxs-lookup"><span data-stu-id="c50f3-166">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="c50f3-167">\- oder -</span><span class="sxs-lookup"><span data-stu-id="c50f3-167">\- or -</span></span>  
  
<span data-ttu-id="c50f3-168">Kommentieren Sie die Compileranweisung aus.</span><span class="sxs-lookup"><span data-stu-id="c50f3-168">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c50f3-169">Wenn Sie kompilieren möchten, können Sie entweder **Erstellen** aus dem Menü **Erstellen** auswählen oder die Befehlszeilenmethode verwenden, allerdings ohne Eingabe von **d:** zum Definieren der Symbole für bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="c50f3-169">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50f3-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50f3-170">See also</span></span>

- [<span data-ttu-id="c50f3-171">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c50f3-171">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="c50f3-172">Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern</span><span class="sxs-lookup"><span data-stu-id="c50f3-172">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="c50f3-173">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="c50f3-173">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="c50f3-174">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="c50f3-174">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="c50f3-175">Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="c50f3-175">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="c50f3-176">Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c50f3-176">How to set environment variables for the Visual Studio Command Line</span></span>](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [<span data-ttu-id="c50f3-177">Vorgehensweise: Aufrufen des Befehlszeilencompilers</span><span class="sxs-lookup"><span data-stu-id="c50f3-177">How to: Invoke the Command-Line Compiler</span></span>](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
