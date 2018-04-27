---
title: 'Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="0c8ae-102">Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c8ae-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="0c8ae-103">Durch den Namen seiner ausführbaren Datei in der Befehlszeile, auch bekannt als MS-DOS, können Sie den Befehlszeilencompiler aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="0c8ae-104">Wenn Sie über die standardmäßige Windows-Befehlszeile kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="0c8ae-105">Um dieses Standardverhalten zu überschreiben, können Sie entweder die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] -Eingabeaufforderung ein, oder ändern Sie die PATH-Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="0c8ae-106">Beide können Sie aus dem Verzeichnis zu kompilieren, indem Sie einfach den Compilernamen.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="0c8ae-107">Zum Aufrufen des Compilers über die Visual Studio-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="0c8ae-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="0c8ae-108">Öffnen Sie den Programmordner Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="0c8ae-109">Sie können die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Befehlszeile aus, um den Compiler aus einem beliebigen Verzeichnis auf Ihrem Computer zugreifen, wenn Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-109">You can use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="0c8ae-110">Aufrufen der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-110">Invoke the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="0c8ae-111">Geben Sie an der Befehlszeile `vbc.exe` *Quelldateiname* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="0c8ae-112">Angenommen, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung, und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="0c8ae-113">Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="0c8ae-114">PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="0c8ae-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="0c8ae-115">Verwenden Sie die Windows-Suchfunktion Vbc.exe auf dem lokalen Datenträger gefunden.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="0c8ae-116">Der genaue Name des Verzeichnisses auf dem sich der Compiler befindet hängt davon ab, den Speicherort des Windows-Verzeichnisses und die Version von ".NET Framework" installiert.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="0c8ae-117">Wenn Sie mehr als eine Version von ".NET Framework" installiert haben, müssen Sie die Version, verwenden Sie (in der Regel die neueste Version) ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="0c8ae-118">Aus Ihrer **starten** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="0c8ae-119">Klicken Sie auf die **erweitert** Registerkarte, und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="0c8ae-120">In der **System** Variablen (Bereich), wählen **Pfad** aus der Liste und klicken Sie auf **bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="0c8ae-121">In der **bearbeiten System** Variable Dialogfeld verschieben Sie die Einfügemarke an das Ende der Zeichenfolge in der **Variablenwert** ein und geben Sie ein Semikolon (;) gefolgt von der vollständiger Verzeichnisname, der in Schritt 1 gefunden.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="0c8ae-122">Klicken Sie auf **OK** die Bearbeitungen bestätigt und die Dialogfelder zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="0c8ae-123">Nachdem Sie die PATH-Umgebungsvariable ändern, können Sie Visual Basic-Compiler an der Windows-Eingabeaufforderung aus dem Verzeichnis auf dem Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="0c8ae-124">Zum Aufrufen des Compilers über die Windows-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="0c8ae-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="0c8ae-125">Aus der **starten** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie dann die **Windows-Befehlszeile**.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="0c8ae-126">Geben Sie an der Befehlszeile `vbc.exe` *Quelldateiname* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="0c8ae-127">Angenommen, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung, und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="0c8ae-128">Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8ae-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c8ae-129">See Also</span></span>  
 [<span data-ttu-id="0c8ae-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0c8ae-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0c8ae-131">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="0c8ae-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
