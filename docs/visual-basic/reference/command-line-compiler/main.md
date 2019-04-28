---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fd6240faf702ccb5e543bfd6a7779284f38d8850
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793912"
---
# <a name="-main"></a><span data-ttu-id="7264b-102">-main</span><span class="sxs-lookup"><span data-stu-id="7264b-102">-main</span></span>
<span data-ttu-id="7264b-103">Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="7264b-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7264b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7264b-104">Syntax</span></span>  
  
```  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="7264b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7264b-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="7264b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7264b-106">Required.</span></span> <span data-ttu-id="7264b-107">Der Name der Klasse oder Modul, enthält die `Sub Main` Prozedur aufgerufen werden, wenn das Programm gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="7264b-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="7264b-108">Dies ist möglicherweise im Formular **-Main: Module** oder **-main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="7264b-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7264b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7264b-109">Remarks</span></span>  
 <span data-ttu-id="7264b-110">Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen.</span><span class="sxs-lookup"><span data-stu-id="7264b-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="7264b-111">Wenn die **-main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in allen öffentlichen Klassen und Modulen.</span><span class="sxs-lookup"><span data-stu-id="7264b-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="7264b-112">Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) eine Erläuterung der verschiedenen Formen von der `Main` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7264b-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="7264b-113">Wenn `location` ist eine Klasse, die von erbt <xref:System.Windows.Forms.Form>, der Compiler stellt eine Standardimplementierung `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine `Main` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7264b-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="7264b-114">Dadurch können Sie den Code in der Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7264b-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="7264b-115">-Main in der integrierten Entwicklungsumgebung von Visual Studio festlegen</span><span class="sxs-lookup"><span data-stu-id="7264b-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="7264b-116">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7264b-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7264b-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7264b-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="7264b-118">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="7264b-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="7264b-119">Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7264b-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="7264b-120">Ändern Sie den Wert in der **Startobjekt** Feld.</span><span class="sxs-lookup"><span data-stu-id="7264b-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7264b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7264b-121">Example</span></span>  
 <span data-ttu-id="7264b-122">Der folgende code kompiliert `T2.vb` und `T3.vb`, geben Sie dabei, die die `Sub Main` Prozedur befindet sich in der `Test2` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7264b-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="7264b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7264b-123">See also</span></span>

- [<span data-ttu-id="7264b-124">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7264b-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7264b-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7264b-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7264b-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7264b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="7264b-127">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7264b-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
