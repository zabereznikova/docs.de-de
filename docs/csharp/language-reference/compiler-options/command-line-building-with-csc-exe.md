---
title: Erstellen über die Befehlszeile mit csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: f692e66672b1804a309c6ac04c158af948a1b1ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789870"
---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="9590b-102">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="9590b-102">Command-line build with csc.exe</span></span>

<span data-ttu-id="9590b-103">Sie können den C#-Compiler aufrufen, indem Sie den Namen seiner ausführbaren Datei (*csc.exe*) in der Befehlszeile eingeben.</span><span class="sxs-lookup"><span data-stu-id="9590b-103">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="9590b-104">Wenn Sie das Fenster **Developer-Eingabeaufforderung für Visual Studio** verwenden, werden alle erforderlichen Umgebungsvariablen für Sie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9590b-104">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="9590b-105">Weitere Informationen zum Zugreifen auf dieses Tool finden Sie unter [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9590b-105">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span>

<span data-ttu-id="9590b-106">Wenn Sie ein standardmäßiges Eingabeaufforderungsfenster verwenden, müssen Sie die Pfadangabe anpassen, bevor Sie *csc.exe* aus einem Unterverzeichnis auf dem Computer aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="9590b-106">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="9590b-107">Außerdem müssen Sie *vsvars32.bat* ausführen, um die entsprechenden Umgebungsvariablen zur Unterstützung von Befehlszeilenbuilds festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9590b-107">You also must run *vsvars32.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="9590b-108">Weitere Informationen zu *vsvars32.bat*, einschließlich Anweisungen zum Suchen und Ausführen, finden Sie unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="9590b-108">For more information about *vsvars32.bat*, including instructions for how to find and run it, see [How to set environment variables for the Visual Studio Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="9590b-109">Wenn Sie auf einem Computer arbeiten, auf dem nur das Windows Software Development Kit (SDK) installiert ist, können Sie den C#-Compiler an der **SDK-Eingabeaufforderung** verwenden. Diese öffnen Sie über die Menüoption **Microsoft .NET Framework SDK**.</span><span class="sxs-lookup"><span data-stu-id="9590b-109">If you're working on a computer that has only the Windows Software Development Kit (SDK), you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="9590b-110">Sie können auch MSBuild verwenden, um C#-Programme programmgesteuert zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9590b-110">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="9590b-111">Weitere Informationen finden Sie unter [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="9590b-111">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="9590b-112">Die ausführbare Datei *csc.exe* befindet sich in der Regel im *Windows*-Verzeichnis im Ordner Microsoft.NET\Framework\\*\<Version>*.</span><span class="sxs-lookup"><span data-stu-id="9590b-112">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="9590b-113">Der Speicherort unterscheidet sich je nach Konfiguration auf den einzelnen Computern.</span><span class="sxs-lookup"><span data-stu-id="9590b-113">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="9590b-114">Wenn mehr als eine Version von .NET Framework auf dem Computer installiert ist, werden Sie mehrere Versionen dieser Datei finden.</span><span class="sxs-lookup"><span data-stu-id="9590b-114">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="9590b-115">Weitere Informationen zu dieser Art von Installation finden Sie unter [How to: determine which versions of the .NET Framework are installed (Vorgehensweise: Bestimmen der installierten .NET Framework-Version)](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="9590b-115">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
> <span data-ttu-id="9590b-116">Wenn Sie ein Projekt mit der Visual Studio-IDE erstellen, können Sie den Befehl **csc** und seine zugeordneten Compileroptionen im Fenster **Ausgabe** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9590b-116">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="9590b-117">Um diese Informationen anzuzeigen, befolgen Sie die Anweisungen in [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log), in denen erläutert wird, wie der Ausführlichkeitsgrad der Protokolldaten in **Normal** oder **Detailliert** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="9590b-117">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="9590b-118">Nachdem Sie das Projekt neu erstellt haben, durchsuchen Sie das Fenster **Ausgabe** nach **csc** nach, um den Aufruf des C#-Compilers zu finden.</span><span class="sxs-lookup"><span data-stu-id="9590b-118">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="9590b-119">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9590b-119">**In this topic**</span></span>

- [<span data-ttu-id="9590b-120">Regeln für die Syntax der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="9590b-120">Rules for command-line syntax</span></span>](#rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="9590b-121">Beispielbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="9590b-121">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="9590b-122">Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="9590b-122">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="9590b-123">Regeln für Befehlszeilensyntax für den C#-Compiler</span><span class="sxs-lookup"><span data-stu-id="9590b-123">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="9590b-124">Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der C#-Compiler die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="9590b-124">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="9590b-125">Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.</span><span class="sxs-lookup"><span data-stu-id="9590b-125">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="9590b-126">Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt.</span><span class="sxs-lookup"><span data-stu-id="9590b-126">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="9590b-127">Das Zeichen wird vom Befehlszeilenparser im Betriebssystem verarbeitet, bevor es an das `argv`-Array im Programm übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9590b-127">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="9590b-128">Eine in Anführungszeichen eingeschlossene Zeichenfolge ("Zeichenfolge") wird als einzelnes Argument interpretiert, auch wenn darin Leerräume enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9590b-128">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="9590b-129">Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.</span><span class="sxs-lookup"><span data-stu-id="9590b-129">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="9590b-130">Wenn dem Anführungszeichen ein umgekehrter Schrägstrich (\\") vorangestellt wird, wird diese Zeichenfolge als literales Anführungszeichen (") interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9590b-130">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="9590b-131">Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.</span><span class="sxs-lookup"><span data-stu-id="9590b-131">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="9590b-132">Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9590b-132">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="9590b-133">Wenn ein doppeltes Anführungszeichen auf eine ungerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das Anführungszeichen wird durch den übrig gebliebenen umgekehrten Schrägstrich maskiert.</span><span class="sxs-lookup"><span data-stu-id="9590b-133">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="9590b-134">Hierdurch wird dem `argv`-Array ein echtes Anführungszeichen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9590b-134">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="9590b-135">Beispielbefehlszeilen für den C#-Compiler</span><span class="sxs-lookup"><span data-stu-id="9590b-135">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="9590b-136">Kompiliert *file.cs*, sodass *file.exe* entsteht:</span><span class="sxs-lookup"><span data-stu-id="9590b-136">Compiles *File.cs* producing *File.exe*:</span></span>

  ```console
  csc File.cs
  ```

- <span data-ttu-id="9590b-137">Kompiliert *file.cs*, sodass *file.exe* entsteht:</span><span class="sxs-lookup"><span data-stu-id="9590b-137">Compiles *File.cs* producing *File.dll*:</span></span>

  ```console
  csc -target:library File.cs
  ```

- <span data-ttu-id="9590b-138">Kompiliert *file.cs* und erstellt *my.exe*:</span><span class="sxs-lookup"><span data-stu-id="9590b-138">Compiles *File.cs* and creates *My.exe*:</span></span>

  ```console
  csc -out:My.exe File.cs
  ```

- <span data-ttu-id="9590b-139">Kompiliert alle C#-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und definiert das DEBUG-Symbol.</span><span class="sxs-lookup"><span data-stu-id="9590b-139">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="9590b-140">Die Ausgabe lautet *File2.exe*:</span><span class="sxs-lookup"><span data-stu-id="9590b-140">The output is *File2.exe*:</span></span>

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- <span data-ttu-id="9590b-141">Kompiliert alle C#-Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von *File2.dll* erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9590b-141">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="9590b-142">Es werden weder Logo noch Warnungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9590b-142">No logo and no warnings are displayed:</span></span>

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- <span data-ttu-id="9590b-143">Kompiliert alle C#-Dateien im aktuellen Verzeichnis zu *Name.xyz* (eine DLL-Datei):</span><span class="sxs-lookup"><span data-stu-id="9590b-143">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="9590b-144">Unterschiede zwischen der C#-Compiler- und der C++-Compiler-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="9590b-144">Differences between C# compiler and C++ compiler output</span></span>

<span data-ttu-id="9590b-145">Durch den Aufruf des C#-Compilers werden keine Objektdateien ( *.obj*) erstellt, stattdessen werden die Ausgabedateien direkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="9590b-145">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="9590b-146">Daher benötigt der C#-Compiler keinen Linker.</span><span class="sxs-lookup"><span data-stu-id="9590b-146">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="9590b-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9590b-147">See also</span></span>

- [<span data-ttu-id="9590b-148">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="9590b-148">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9590b-149">C#-Compileroptionen alphabetisch sortiert</span><span class="sxs-lookup"><span data-stu-id="9590b-149">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
- [<span data-ttu-id="9590b-150">C#-Compileroptionen nach Kategorien sortiert</span><span class="sxs-lookup"><span data-stu-id="9590b-150">C# Compiler Options Listed by Category</span></span>](./listed-by-category.md)
- [<span data-ttu-id="9590b-151">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="9590b-151">Main() and Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="9590b-152">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="9590b-152">Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [<span data-ttu-id="9590b-153">Vorgehensweise: Anzeigen von Befehlszeilenargumenten</span><span class="sxs-lookup"><span data-stu-id="9590b-153">How to display command-line arguments</span></span>](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="9590b-154">Main()-Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="9590b-154">Main() Return Values</span></span>](../../programming-guide/main-and-command-args/main-return-values.md)
