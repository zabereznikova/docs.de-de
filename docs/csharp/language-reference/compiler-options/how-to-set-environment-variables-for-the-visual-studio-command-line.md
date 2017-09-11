---
title: "Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="9efab-102">Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="9efab-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>
<span data-ttu-id="9efab-103">Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSVARS32.BAT festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9efab-103">The vsvars32.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="9efab-104">Weitere Informationen zu „vsvars32.bat“ finden Sie im [Knowledge Base-Artikel Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="9efab-104">For more information about vsvars32.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  
  
 <span data-ttu-id="9efab-105">Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VSVARS32.BAT und VCVARS32.BAT nicht aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="9efab-105">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run vsvars32.bat or vcvars32.bat from different versions in the same Command Prompt window.</span></span>  
  
### <a name="to-run-vsvars32bat"></a><span data-ttu-id="9efab-106">So führen Sie VSVARS32.BAT aus</span><span class="sxs-lookup"><span data-stu-id="9efab-106">To run VSVARS32.BAT</span></span>  
  
1.  <span data-ttu-id="9efab-107">Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS2012**.</span><span class="sxs-lookup"><span data-stu-id="9efab-107">From the **Start** menu, open the **Developer Command Prompt for VS2012**.</span></span>  
  
2.  <span data-ttu-id="9efab-108">Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio *Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio *Version*\Common7\Tools“ Ihrer Installation.</span><span class="sxs-lookup"><span data-stu-id="9efab-108">Change to the Program Files\Microsoft Visual Studio *Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools subdirectory of your installation.</span></span>  
  
3.  <span data-ttu-id="9efab-109">Führen Sie „VSVARS32.BAT“ aus, indem Sie **VSVARS32** eingeben.</span><span class="sxs-lookup"><span data-stu-id="9efab-109">Run VSVARS32.bat by typing **VSVARS32**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="9efab-110">VSVARS32.BAT kann auf verschiedenen Computern unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="9efab-110">VSVARS32.bat can vary from computer to computer.</span></span> <span data-ttu-id="9efab-111">Falls die Datei VSVARS32.BAT nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VSVARS32.BAT-Datei eines anderen Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9efab-111">Do not replace a missing or damaged VSVARS32.bat file with a VSVARS32.bat from another computer.</span></span> <span data-ttu-id="9efab-112">Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9efab-112">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efab-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9efab-113">See Also</span></span>  
 [<span data-ttu-id="9efab-114">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="9efab-114">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

