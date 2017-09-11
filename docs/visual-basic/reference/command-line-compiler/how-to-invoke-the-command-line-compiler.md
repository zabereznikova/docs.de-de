---
title: 'Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e19bb506b016b774d2c497f8b17d91b35afb3eef
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="bcd9f-102">Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd9f-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="bcd9f-103">Sie können den Befehlszeilencompiler aufrufen, durch den Namen seiner ausführbaren Datei in der Befehlszeile angeben, auch bekannt als MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="bcd9f-104">Wenn Sie über die Standard-Windows-Befehlszeile kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="bcd9f-105">Um dieses Standardverhalten zu überschreiben, können Sie entweder die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] -Eingabeaufforderungsfenster aus, oder ändern Sie die PATH-Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="bcd9f-106">Beide ermöglichen es Ihnen, einfach den Compilernamen aus dem Verzeichnis zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="bcd9f-107">Zum Aufrufen des Compilers mithilfe der Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="bcd9f-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="bcd9f-108">Öffnen Sie den Programmordner von Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="bcd9f-109">Sie können die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Befehlszeile aus, um den Compiler aus dem Verzeichnis auf Ihrem Computer zugreifen, wenn Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-109">You can use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="bcd9f-110">Aufrufen der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-110">Invoke the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="bcd9f-111">Geben Sie an der Befehlszeile `vbc.exe` *SourceFileName* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="bcd9f-112">Beispielsweise, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Befehlszeile und den Typ `cd SourceFiles` in dieses Verzeichnis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="bcd9f-113">Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="bcd9f-114">Die PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="bcd9f-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="bcd9f-115">Verwenden Sie die Windows-Suchfunktion Vbc.exe auf dem lokalen Datenträger gefunden.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="bcd9f-116">Der genaue Name des Verzeichnisses, in dem der Compiler befindet, hängt von den Speicherort des Windows-Verzeichnisses und die Version der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installiert.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed.</span></span> <span data-ttu-id="bcd9f-117">Wenn Sie mehr als eine Version von ist die [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installiert haben, müssen Sie bestimmen, welche Version verwendet (in der Regel die neueste Version).</span><span class="sxs-lookup"><span data-stu-id="bcd9f-117">If you have more than one version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="bcd9f-118">Aus der **Start** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="bcd9f-119">Klicken Sie auf die **erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="bcd9f-120">In der **System** Variablen Bereich **Pfad** aus der Liste aus und klicken Sie auf **bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="bcd9f-121">In der **bearbeiten** Variable Dialogfeld verschieben Sie die Einfügemarke an das Ende der Zeichenfolge in der **Variablenwert** aus, und geben Sie ein Semikolon (;) gefolgt vom vollständigen Verzeichnisnamen aus Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="bcd9f-122">Klicken Sie auf **OK** Ihre Änderungen zu bestätigen und das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="bcd9f-123">Nachdem Sie die PATH-Umgebungsvariable geändert haben, können Sie Ausführen den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler an der Windows-Befehlszeile aus dem Verzeichnis auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-123">After you change the PATH environment variable, you can run the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="bcd9f-124">Zum Aufrufen des Compilers mithilfe der Windows-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="bcd9f-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="bcd9f-125">Aus der **Start** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie die **Windows-Befehlszeile**.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="bcd9f-126">Geben Sie an der Befehlszeile `vbc.exe` *SourceFileName* und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="bcd9f-127">Beispielsweise, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Befehlszeile und den Typ `cd SourceFiles` in dieses Verzeichnis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="bcd9f-128">Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="bcd9f-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd9f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcd9f-129">See Also</span></span>  
 <span data-ttu-id="bcd9f-130">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="bcd9f-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="bcd9f-131"> [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="bcd9f-131"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
