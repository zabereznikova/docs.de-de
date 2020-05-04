---
title: 'Vorgehensweise: Aufrufen des Befehlszeilencompilers'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344261"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="4347a-102">Vorgehensweise: Aufrufen des Befehlszeilencompilers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4347a-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="4347a-103">Sie können den Befehlszeilencompiler aufrufen, indem Sie den Namen der ausführbaren Datei in die Befehlszeile eingeben (auch bekannt als MS-DOS-Eingabeaufforderung).</span><span class="sxs-lookup"><span data-stu-id="4347a-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="4347a-104">Wenn Sie über die Windows-Standardeingabeaufforderung kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="4347a-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="4347a-105">Sie können entweder die Developer-Eingabeaufforderung für Visual Studio verwenden oder die PATH-Umgebungsvariable ändern, um dieses Standardverhalten zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="4347a-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="4347a-106">Beide Varianten ermöglichen die Kompilierung aus einem beliebigen Verzeichnis, indem Sie einfach den Compilernamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="4347a-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="4347a-107">Aufrufen des Compilers mithilfe der Developer-Eingabeaufforderung für Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4347a-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="4347a-108">Öffnen Sie den Visual Studio Tools-Programmordner in der Microsoft Visual Studio-Programmgruppe.</span><span class="sxs-lookup"><span data-stu-id="4347a-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="4347a-109">Wenn Visual Studio installiert ist, können Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, um von einem beliebigen Verzeichnis auf Ihrem Computer aus auf den Compiler zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4347a-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="4347a-110">Rufen Sie die Developer-Eingabeaufforderung für Visual Studio auf.</span><span class="sxs-lookup"><span data-stu-id="4347a-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="4347a-111">Geben Sie in der Befehlszeile `vbc.exe` *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4347a-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="4347a-112">Wenn Sie z. B. den Quellcode in einem Verzeichnis namens `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung, und geben Sie `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4347a-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="4347a-113">Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthält, können Sie es durch die Eingabe von `vbc.exe Source.vb` kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4347a-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="4347a-114">Festlegen der PATH-Umgebungsvariable auf den Compiler für die Windows-Eingabeaufforderung fest</span><span class="sxs-lookup"><span data-stu-id="4347a-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="4347a-115">Verwenden Sie die Windows-Suchfunktion für die Suche nach Vbc.exe auf Ihrem lokalen Datenträger.</span><span class="sxs-lookup"><span data-stu-id="4347a-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="4347a-116">Der genaue Name des Verzeichnisses, in dem sich der Compiler befindet, hängt vom Speicherort des Windows-Verzeichnisses und der installierten Version von „.NET Framework“ ab.</span><span class="sxs-lookup"><span data-stu-id="4347a-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="4347a-117">Wenn mehr als eine Version von „.NET Framework“ installiert ist, müssen Sie festlegen, welche Version verwendet werden soll (in der Regel die neueste Version).</span><span class="sxs-lookup"><span data-stu-id="4347a-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="4347a-118">Klicken Sie im **Startmenü** zunächst mit der rechten Maustaste auf **Arbeitsplatz** und dann im Kontextmenü auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4347a-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="4347a-119">Klicken Sie auf die Registerkarte **Erweitert**und dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="4347a-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="4347a-120">Klicken Sie im Bereich **Systemvariablen** in der Liste auf **Pfad** und dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4347a-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="4347a-121">Verschieben Sie im Dialogfeld **Systemvariable bearbeiten** die Einfügemarke an das Ende der Zeichenfolge im Feld **Variablenwert**, und geben Sie ein Semikolon (;) gefolgt vom vollständigen Verzeichnisnamen aus Schritt 1 ein.</span><span class="sxs-lookup"><span data-stu-id="4347a-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="4347a-122">Klicken Sie auf **OK**, um die Änderungen zu bestätigen und die Dialogfelder zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4347a-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="4347a-123">Nachdem Sie die PATH-Umgebungsvariable geändert haben, können Sie den Visual Basic-Compiler von einem beliebigen Verzeichnis auf dem Computer aus in der Windows-Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4347a-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="4347a-124">Aufrufen des Compilers mithilfe der Windows-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="4347a-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="4347a-125">Klicken Sie im **Startmenü** auf den Ordner **Zubehör**, und öffnen Sie dann die **Windows-Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="4347a-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="4347a-126">Geben Sie in der Befehlszeile `vbc.exe` *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4347a-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="4347a-127">Wenn Sie z. B. den Quellcode in einem Verzeichnis namens `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung, und geben Sie `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4347a-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="4347a-128">Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthält, können Sie es durch die Eingabe von `vbc.exe Source.vb` kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4347a-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4347a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4347a-129">See also</span></span>

- [<span data-ttu-id="4347a-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4347a-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4347a-131">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="4347a-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
