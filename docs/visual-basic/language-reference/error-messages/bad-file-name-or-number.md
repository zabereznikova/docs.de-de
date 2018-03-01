---
title: "Der Dateiname oder die Zahl ist ungültig."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="5af7e-102">Der Dateiname oder die Zahl ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5af7e-102">Bad file name or number</span></span>
<span data-ttu-id="5af7e-103">Fehler beim Versuch, auf die angegebene Datei zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5af7e-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="5af7e-104">Zu den möglichen Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="5af7e-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="5af7e-105">Eine Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Zahl, die nicht im angegebenen der `FileOpen` -Anweisung oder, im angegebenen wurde eine `FileOpen` Anweisung statt anschließend geschlossen.</span><span class="sxs-lookup"><span data-stu-id="5af7e-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="5af7e-106">Eine Anweisung verweist auf eine Datei mit einer Zahl, die außerhalb des Bereichs der Datei Zahlen ist.</span><span class="sxs-lookup"><span data-stu-id="5af7e-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="5af7e-107">Eine Anweisung verweist auf einen Dateinamen oder eine Zahl, die nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="5af7e-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5af7e-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5af7e-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="5af7e-109">Stellen Sie sicher, dass der Dateiname ist angegeben, eine `FileOpen` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5af7e-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="5af7e-110">Beachten Sie, dass, wenn Sie aufgerufen, die `FileClose` Anweisung ohne Argumente, Sie möglicherweise versehentlich geschlossen haben alle geöffneten Dateien.</span><span class="sxs-lookup"><span data-stu-id="5af7e-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="5af7e-111">Wenn Ihr Code Datei Zahlen algorithmisch generiert, stellen Sie sicher, dass die Zahlen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="5af7e-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="5af7e-112">Überprüfen Sie die Dateinamen, um sicherzustellen, dass sie Betriebssystem-Konventionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5af7e-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af7e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5af7e-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="5af7e-114">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="5af7e-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
