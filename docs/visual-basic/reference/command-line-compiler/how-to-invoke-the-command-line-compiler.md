---
title: 'Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 0b835bb5654574a5aa6f32eede1e942b11e7dcb0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932153"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="66878-102">Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66878-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="66878-103">Sie können den Befehlszeilencompiler aufrufen, geben Sie den Namen seiner ausführbaren Datei in die Befehlszeile, auch bekannt als die MS-DOS-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="66878-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="66878-104">Wenn Sie von der Standard-Windows-Eingabeaufforderung kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="66878-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="66878-105">Um dieses Standardverhalten zu überschreiben, können Sie entweder die Visual Studio-Eingabeaufforderung verwenden, oder Ändern der PATH-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="66878-105">To override this default behavior, you can either use the Visual Studio Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="66878-106">Beide können Sie aus dem Verzeichnis zu kompilieren, indem Sie einfach den Compilernamen.</span><span class="sxs-lookup"><span data-stu-id="66878-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="66878-107">Zum Aufrufen des Compilers mit dem Visual Studio-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="66878-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="66878-108">Der Programmordner des Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="66878-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="66878-109">Sie können die Visual Studio-Eingabeaufforderung verwenden, den Compiler aus dem Verzeichnis auf Ihrem Computer, den Zugriff auf, wenn Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="66878-109">You can use the Visual Studio Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="66878-110">Rufen Sie die Visual Studio-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="66878-110">Invoke the Visual Studio Command Prompt.</span></span>  
  
4.  <span data-ttu-id="66878-111">Geben Sie an der Befehlszeile `vbc.exe` *"sourceFileName"* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="66878-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="66878-112">Z. B., wenn Sie Ihren Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="66878-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="66878-113">Wenn das Verzeichnis eine Quellcodedatei namens enthalten `Source.vb`, können Sie diese kompilieren, indem Sie eingeben `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="66878-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="66878-114">Der PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="66878-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="66878-115">Verwenden Sie die Windows Search-Funktion, um Vbc.exe auf dem lokalen Datenträger suchen.</span><span class="sxs-lookup"><span data-stu-id="66878-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="66878-116">Der genaue Name des Verzeichnisses, in denen der Compiler befindet, hängt davon ab, der Speicherort des Windows-Verzeichnisses und die Version von ".NET Framework" installiert.</span><span class="sxs-lookup"><span data-stu-id="66878-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="66878-117">Wenn Sie mehr als eine Version von ".NET Framework" installiert haben, müssen Sie feststellen, welcher Version (in der Regel die neueste Version) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66878-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="66878-118">Aus Ihrem **starten** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="66878-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="66878-119">Klicken Sie auf die **erweitert** Registerkarte, und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="66878-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="66878-120">In der **System** wählen Sie im Variablenbereich **Pfad** aus der Liste und klicken Sie auf **bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="66878-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="66878-121">In der **bearbeiten System** Variable Dialogfeld Verschieben der Einfügemarke bis zum Ende der Zeichenfolge in die **Variablenwert** ein, und geben Sie ein Semikolon (;) gefolgt von der vollständigen Verzeichnisnamen, die in Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="66878-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="66878-122">Klicken Sie auf **OK** die Bearbeitungen bestätigt und die Dialogfelder zu schließen.</span><span class="sxs-lookup"><span data-stu-id="66878-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="66878-123">Nachdem Sie der PATH-Umgebungsvariablen ändern, können Sie Visual Basic-Compiler an der Windows-Eingabeaufforderung aus dem Verzeichnis auf dem Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="66878-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="66878-124">Zum Aufrufen des Compilers mithilfe der Windows-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="66878-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="66878-125">Von der **starten** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie die **Windows-Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="66878-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="66878-126">Geben Sie an der Befehlszeile `vbc.exe` *"sourceFileName"* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="66878-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="66878-127">Z. B., wenn Sie Ihren Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="66878-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="66878-128">Wenn das Verzeichnis eine Quellcodedatei namens enthalten `Source.vb`, können Sie diese kompilieren, indem Sie eingeben `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="66878-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66878-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66878-129">See Also</span></span>  
 [<span data-ttu-id="66878-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="66878-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="66878-131">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="66878-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
