---
title: 'Gewusst wie: Erstellen eines Verzeichnisses'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 3d838352a0a3dd69a1555dc34b8acba3afba278b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348813"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="57d44-102">Gewusst wie: Erstellen eines Verzeichnisses in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57d44-102">How to: Create a Directory in Visual Basic</span></span>

<span data-ttu-id="57d44-103">Verwenden Sie die `CreateDirectory`-Methode des `My.Computer.FileSystem`-Objekts, um Verzeichnisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57d44-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="57d44-104">Wenn das Verzeichnis bereits vorhanden ist, werden keine Ausnahmen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57d44-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="57d44-105">So erstellen Sie ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="57d44-105">To create a directory</span></span>  
  
- <span data-ttu-id="57d44-106">Verwenden Sie die `CreateDirectory`-Methode, indem Sie den vollständigen Pfad des Speicherorts angeben, an dem das Verzeichnis erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="57d44-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="57d44-107">Dieses Beispiel erstellt das Verzeichnis `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="57d44-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="57d44-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="57d44-108">Robust Programming</span></span>  

 <span data-ttu-id="57d44-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="57d44-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="57d44-110">Der Name des Verzeichnisses ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="57d44-110">The directory name is malformed.</span></span> <span data-ttu-id="57d44-111">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="57d44-112">Das übergeordnete Verzeichnis des zu erstellenden Verzeichnisses ist schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="57d44-113">Der Name des Verzeichnisses ist `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="57d44-114">Der Name des Verzeichnisses ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="57d44-115">Der Name des Verzeichnisses ist ein Doppelpunkt „:“ (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="57d44-116">Der Benutzer verfügt über keine Berechtigungen zum Erstellen des Verzeichnisses (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="57d44-117">Der Benutzer verfügt über keine Berechtigung in einem teilweise vertrauenswürdigen Kontext (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="57d44-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d44-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57d44-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="57d44-119">Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="57d44-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
