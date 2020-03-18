---
title: 'Gewusst wie: Erstellen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: 20533ec01d3198d499312ed0c15ec8cca2ff70bd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348801"
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="1ee2b-102">Gewusst wie: Erstellen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ee2b-102">How to: Create a File in Visual Basic</span></span>

<span data-ttu-id="1ee2b-103">Dieses Beispiel erstellt mithilfe der <xref:System.IO.File.Create%2A>-Methode in der <xref:System.IO.File>-Klasse eine leere Textdatei auf dem bestimmten Pfad.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ee2b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ee2b-104">Example</span></span>  

 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ee2b-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1ee2b-105">Compiling the Code</span></span>  

 <span data-ttu-id="1ee2b-106">Verwenden Sie die Varible `file`, um in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1ee2b-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="1ee2b-107">Robust Programming</span></span>  

 <span data-ttu-id="1ee2b-108">Wenn die Datei bereits vorhanden ist, wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="1ee2b-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="1ee2b-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1ee2b-110">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-110">The path name is malformed.</span></span> <span data-ttu-id="1ee2b-111">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="1ee2b-112">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="1ee2b-113">Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="1ee2b-114">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="1ee2b-115">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="1ee2b-116">Der Pfad besteht nur aus einem Doppelpunkt „:“ (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="1ee2b-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1ee2b-117">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1ee2b-117">.NET Framework Security</span></span>  

 <span data-ttu-id="1ee2b-118">Eine <xref:System.Security.SecurityException> wir möglicherweise in teilweise vertrauenswürdigen Umgebungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="1ee2b-119">Der Aufruf auf die <xref:System.IO.File.Create%2A>-Methode erfordert <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="1ee2b-120">Eine <xref:System.UnauthorizedAccessException> wird ausgelöst, wenn der Benutzer keine Berechtigungen zum Erstellen der Datei besitzt.</span><span class="sxs-lookup"><span data-stu-id="1ee2b-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee2b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ee2b-121">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [<span data-ttu-id="1ee2b-122">Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code</span><span class="sxs-lookup"><span data-stu-id="1ee2b-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [<span data-ttu-id="1ee2b-123">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="1ee2b-123">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
