---
title: 'Gewusst wie: Erstellen eines Verzeichnisses in Visual Basic'
ms.custom: 
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
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a45a785916b480dcee6e36fd295390266eaa0a0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="89a84-102">Gewusst wie: Erstellen eines Verzeichnisses in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89a84-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="89a84-103">Verwenden Sie die `CreateDirectory`-Methode des `My.Computer.FileSystem`-Objekts, um Verzeichnisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89a84-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="89a84-104">Wenn das Verzeichnis bereits vorhanden ist, werden keine Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="89a84-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="89a84-105">So erstellen Sie ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="89a84-105">To create a directory</span></span>  
  
-   <span data-ttu-id="89a84-106">Verwenden Sie die `CreateDirectory`-Methode, indem Sie den vollständigen Pfad des Speicherorts angeben, an dem das Verzeichnis erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89a84-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="89a84-107">Dieses Beispiel erstellt das Verzeichnis `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="89a84-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     <span data-ttu-id="89a84-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="89a84-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="89a84-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="89a84-109">Robust Programming</span></span>  
 <span data-ttu-id="89a84-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="89a84-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="89a84-111">Der Name des Verzeichnisses ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="89a84-111">The directory name is malformed.</span></span> <span data-ttu-id="89a84-112">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="89a84-113">Das übergeordnete Verzeichnis des zu erstellenden Verzeichnisses ist schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="89a84-114">Der Name des Verzeichnisses ist `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="89a84-115">Der Name des Verzeichnisses ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="89a84-116">Der Name des Verzeichnisses ist ein Doppelpunkt „:“ (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="89a84-117">Der Benutzer verfügt über keine Berechtigungen zum Erstellen des Verzeichnisses (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="89a84-118">Der Benutzer verfügt über keine Berechtigung in einem teilweise vertrauenswürdigen Kontext (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="89a84-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a84-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89a84-119">See Also</span></span>  
 <span data-ttu-id="89a84-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="89a84-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span></span>   
 [<span data-ttu-id="89a84-121">Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="89a84-121">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)

