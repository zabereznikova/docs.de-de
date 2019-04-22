---
title: 'Vorgehensweise: Erstellen einer Datei in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: a05e73a2096c82c9299e4483bbaf69e560fc2e45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839417"
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="b5458-102">Vorgehensweise: Erstellen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5458-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="b5458-103">Dieses Beispiel erstellt mithilfe der <xref:System.IO.File.Create%2A>-Methode in der <xref:System.IO.File>-Klasse eine leere Textdatei auf dem bestimmten Pfad.</span><span class="sxs-lookup"><span data-stu-id="b5458-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5458-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5458-104">Example</span></span>  
 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5458-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b5458-105">Compiling the Code</span></span>  
 <span data-ttu-id="b5458-106">Verwenden Sie die Varible `file`, um in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b5458-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b5458-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b5458-107">Robust Programming</span></span>  
 <span data-ttu-id="b5458-108">Wenn die Datei bereits vorhanden ist, wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b5458-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="b5458-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b5458-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b5458-110">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="b5458-110">The path name is malformed.</span></span> <span data-ttu-id="b5458-111">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="b5458-112">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="b5458-113">Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="b5458-114">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="b5458-115">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="b5458-116">Der Pfad besteht nur aus einem Doppelpunkt „:“ (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b5458-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b5458-117">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b5458-117">.NET Framework Security</span></span>  
 <span data-ttu-id="b5458-118">Eine <xref:System.Security.SecurityException> wir möglicherweise in teilweise vertrauenswürdigen Umgebungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b5458-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="b5458-119">Der Aufruf auf die <xref:System.IO.File.Create%2A>-Methode erfordert <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="b5458-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="b5458-120">Eine <xref:System.UnauthorizedAccessException> wird ausgelöst, wenn der Benutzer keine Berechtigungen zum Erstellen der Datei besitzt.</span><span class="sxs-lookup"><span data-stu-id="b5458-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5458-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5458-121">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [<span data-ttu-id="b5458-122">Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code</span><span class="sxs-lookup"><span data-stu-id="b5458-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [<span data-ttu-id="b5458-123">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="b5458-123">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
