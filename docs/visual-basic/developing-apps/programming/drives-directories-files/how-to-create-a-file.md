---
title: 'Vorgehensweise: Erstellen einer Datei'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: 20533ec01d3198d499312ed0c15ec8cca2ff70bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348801"
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="32365-102">Vorgehensweise: Erstellen einer Datei in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32365-102">How to: Create a File in Visual Basic</span></span>

<span data-ttu-id="32365-103">Dieses Beispiel erstellt mithilfe der <xref:System.IO.File.Create%2A>-Methode in der <xref:System.IO.File>-Klasse eine leere Textdatei auf dem bestimmten Pfad.</span><span class="sxs-lookup"><span data-stu-id="32365-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32365-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32365-104">Example</span></span>  

 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32365-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="32365-105">Compiling the Code</span></span>  

 <span data-ttu-id="32365-106">Verwenden Sie die Varible `file`, um in die Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="32365-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="32365-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="32365-107">Robust Programming</span></span>  

 <span data-ttu-id="32365-108">Wenn die Datei bereits vorhanden ist, wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="32365-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="32365-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="32365-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="32365-110">Der Pfadname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="32365-110">The path name is malformed.</span></span> <span data-ttu-id="32365-111">Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="32365-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="32365-112">Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="32365-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="32365-113">Der Pfadname ist `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="32365-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="32365-114">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="32365-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="32365-115">Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="32365-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="32365-116">Der Pfad besteht nur aus einem Doppelpunkt „:“ (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="32365-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="32365-117">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="32365-117">.NET Framework Security</span></span>  

 <span data-ttu-id="32365-118">Eine <xref:System.Security.SecurityException> wir möglicherweise in teilweise vertrauenswürdigen Umgebungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="32365-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="32365-119">Der Aufruf auf die <xref:System.IO.File.Create%2A>-Methode erfordert <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="32365-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="32365-120">Eine <xref:System.UnauthorizedAccessException> wird ausgelöst, wenn der Benutzer keine Berechtigungen zum Erstellen der Datei besitzt.</span><span class="sxs-lookup"><span data-stu-id="32365-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32365-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32365-121">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [<span data-ttu-id="32365-122">Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code</span><span class="sxs-lookup"><span data-stu-id="32365-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [<span data-ttu-id="32365-123">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="32365-123">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
