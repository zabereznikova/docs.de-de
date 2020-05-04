---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005506"
---
# <a name="-main"></a><span data-ttu-id="819c1-102">-main</span><span class="sxs-lookup"><span data-stu-id="819c1-102">-main</span></span>
<span data-ttu-id="819c1-103">Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="819c1-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="819c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="819c1-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="819c1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="819c1-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="819c1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="819c1-106">Required.</span></span> <span data-ttu-id="819c1-107">Der Name der Klasse oder des Moduls mit der `Sub Main`-Prozedur, die beim Programmstart aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="819c1-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="819c1-108">Dieser kann als **-main:module** oder **-main:namespace.module** vorliegen.</span><span class="sxs-lookup"><span data-stu-id="819c1-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="819c1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="819c1-109">Remarks</span></span>  
 <span data-ttu-id="819c1-110">Diese Option ist geeignet, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen.</span><span class="sxs-lookup"><span data-stu-id="819c1-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="819c1-111">Wird die Option **-main** nicht angegeben, sucht der Compiler in allen öffentlichen Klassen und Modulen nach einer gültigen freigegebenen `Sub Main`-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="819c1-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="819c1-112">Informationen zu den verschiedenen Formularen der `Main`-Prozedur finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="819c1-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="819c1-113">Ist `location` eine Klasse, die von <xref:System.Windows.Forms.Form> erbt, stellt der Compiler eine `Main`-Standardprozedur bereit, mit der die Anwendung gestartet wird, wenn die Klasse keine `Main`-Prozedur enthält.</span><span class="sxs-lookup"><span data-stu-id="819c1-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="819c1-114">Auf diese Weise können Sie Code in der Befehlszeile kompilieren, der in der Entwicklungsumgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="819c1-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="819c1-115">So legen Sie „-main“ in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="819c1-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="819c1-116">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="819c1-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="819c1-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="819c1-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="819c1-118">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="819c1-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="819c1-119">Stellen Sie sicher, dass das Kontrollkästchen bei **Anwendungsframework aktivieren** nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="819c1-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="819c1-120">Ändern Sie die den Wert im Feld **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="819c1-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="819c1-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="819c1-121">Example</span></span>  
 <span data-ttu-id="819c1-122">Mit dem folgenden Code werden `T2.vb` und `T3.vb` kompiliert. Dabei wird angegeben, dass sich die `Sub Main`-Prozedur in der `Test2`-Klasse befindet.</span><span class="sxs-lookup"><span data-stu-id="819c1-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="819c1-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="819c1-123">See also</span></span>

- [<span data-ttu-id="819c1-124">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="819c1-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="819c1-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="819c1-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="819c1-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="819c1-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="819c1-127">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="819c1-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
