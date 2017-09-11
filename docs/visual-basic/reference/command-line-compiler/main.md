---
title: / main | Microsoft-Dokumentation
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
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: 61aa78e131ba8903035f630a540f49848f1acd3f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="main"></a><span data-ttu-id="881af-102">/main</span><span class="sxs-lookup"><span data-stu-id="881af-102">/main</span></span>
<span data-ttu-id="881af-103">Gibt die Klasse oder das Modul, enthält das `Sub Main` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="881af-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="881af-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="881af-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="881af-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="881af-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="881af-106">Required.</span></span> <span data-ttu-id="881af-107">Eine vollständige Qualifizierung der Klasse oder des Moduls mit dem `Sub Main` Prozedur aufgerufen werden, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="881af-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="881af-108">Dies ist möglicherweise im Formular **/main:module** oder **Namespace.Module angegeben**.</span><span class="sxs-lookup"><span data-stu-id="881af-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="881af-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="881af-109">Remarks</span></span>  
 <span data-ttu-id="881af-110">Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen.</span><span class="sxs-lookup"><span data-stu-id="881af-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="881af-111">Wenn die **/main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in allen öffentlichen Klassen und Modulen.</span><span class="sxs-lookup"><span data-stu-id="881af-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="881af-112">Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) eine Erläuterung der verschiedenen Formen von der `Main` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="881af-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="881af-113">Wenn `location` ist eine Klasse, die von erbt <xref:System.Windows.Forms.Form>, stellt der Compiler eine `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine `Main` Verfahren.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="881af-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="881af-114">Dadurch können Sie den Code in der Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="881af-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 <span data-ttu-id="881af-115">[!code-vb[VbVbalrCompiler Nr.&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="881af-115">[!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span></span>  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="881af-116">Zum Festlegen von/Main in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="881af-116">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="881af-117">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="881af-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="881af-118">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="881af-118">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="881af-119">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="881af-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="881af-120">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="881af-120">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="881af-121">Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="881af-121">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="881af-122">Ändern Sie den Wert in der **Startobjekt** Feld.</span><span class="sxs-lookup"><span data-stu-id="881af-122">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="881af-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="881af-123">Example</span></span>  
 <span data-ttu-id="881af-124">Der folgende code kompiliert `T2.vb` und `T3.vb`, angeben, die die `Sub Main` Prozedur befindet sich in der `Test2` Klasse.</span><span class="sxs-lookup"><span data-stu-id="881af-124">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="881af-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="881af-125">See Also</span></span>  
 <span data-ttu-id="881af-126">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="881af-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="881af-127"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="881af-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="881af-128"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="881af-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="881af-129"> [NIB: Visual Basic-Version von Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span><span class="sxs-lookup"><span data-stu-id="881af-129"> [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span></span>  
<span data-ttu-id="881af-130"> [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="881af-130"> [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span></span>
