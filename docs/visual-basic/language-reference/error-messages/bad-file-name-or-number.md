---
title: Der Dateiname oder die Zahl ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 7a16e951030731bdcbb48b5fbb1a0d1881d5e1ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619393"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="6f8bb-102">Der Dateiname oder die Zahl ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-102">Bad file name or number</span></span>
<span data-ttu-id="6f8bb-103">Fehler beim Versuch, die die angegebene Datei zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="6f8bb-104">Zu den möglichen Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="6f8bb-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="6f8bb-105">Eine Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Zahl, die nicht in angegeben wurde der `FileOpen` -Anweisung oder die wurde angegeben, eine `FileOpen` -Anweisung war jedoch anschließend geschlossen.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="6f8bb-106">Eine Anweisung verweist auf eine Datei mit der eine Zahl, die außerhalb des Bereichs der Datei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="6f8bb-107">Eine Anweisung verweist auf einen Dateinamen oder eine Zahl, die nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f8bb-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6f8bb-108">To correct this error</span></span>  
  
1. <span data-ttu-id="6f8bb-109">Stellen Sie sicher, dass der Dateiname ist angegeben, einem `FileOpen` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="6f8bb-110">Beachten Sie, dass Sie aufgerufen haben die `FileClose` Anweisung ohne Argumente, Sie möglicherweise versehentlich geschlossen haben alle geöffneten Dateien.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="6f8bb-111">Wenn Ihr Code Dateinummern algorithmisch generiert, stellen Sie sicher, dass die Zahlen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="6f8bb-112">Überprüfen Sie die Dateinamen, um sicherzustellen, dass sie den Betriebssystem-Konventionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6f8bb-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8bb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f8bb-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="6f8bb-114">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="6f8bb-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
