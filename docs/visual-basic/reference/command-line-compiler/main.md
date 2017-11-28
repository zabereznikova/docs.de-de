---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a><span data-ttu-id="4f632-102">/main</span><span class="sxs-lookup"><span data-stu-id="4f632-102">/main</span></span>
<span data-ttu-id="4f632-103">Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="4f632-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f632-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f632-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f632-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4f632-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="4f632-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4f632-106">Required.</span></span> <span data-ttu-id="4f632-107">Eine vollständige Qualifizierung der Klasse oder ein Modul mit der `Sub Main` Prozedur aufgerufen werden, wenn das Programm gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4f632-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="4f632-108">Dies ist möglicherweise im Formular **/main:module** oder **Namespace.Module angegeben**.</span><span class="sxs-lookup"><span data-stu-id="4f632-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f632-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f632-109">Remarks</span></span>  
 <span data-ttu-id="4f632-110">Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f632-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="4f632-111">Wenn die **/main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in alle öffentlichen Klassen und Module.</span><span class="sxs-lookup"><span data-stu-id="4f632-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="4f632-112">Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) für eine Erläuterung zu den verschiedenen Formen von der `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4f632-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="4f632-113">Wenn `location` ist eine Klasse, die von erben <xref:System.Windows.Forms.Form>, gibt der Compiler eine `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine enthält `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4f632-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="4f632-114">Dadurch können Sie den Code über die Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4f632-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="4f632-115">Zum Festlegen von/Main in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="4f632-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="4f632-116">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4f632-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4f632-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4f632-117">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="4f632-118">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="4f632-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="4f632-119">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="4f632-119">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="4f632-120">Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4f632-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="4f632-121">Ändern Sie den Wert in der **Startobjekt** Feld.</span><span class="sxs-lookup"><span data-stu-id="4f632-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f632-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f632-122">Example</span></span>  
 <span data-ttu-id="4f632-123">Der folgende code kompiliert `T2.vb` und `T3.vb`, und geben, die die `Sub Main` Prozedur befinden sich der `Test2` Klasse.</span><span class="sxs-lookup"><span data-stu-id="4f632-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f632-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f632-124">See Also</span></span>  
 [<span data-ttu-id="4f632-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4f632-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4f632-126">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f632-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="4f632-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4f632-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="4f632-128">NIB: Visual Basic-Version von Hello, World</span><span class="sxs-lookup"><span data-stu-id="4f632-128">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="4f632-129">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f632-129">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
