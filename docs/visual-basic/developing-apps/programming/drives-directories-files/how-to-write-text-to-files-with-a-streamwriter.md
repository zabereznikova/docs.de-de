---
title: 'Gewusst wie: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic'
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
- files, writing to
- text, writing to files
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
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
ms.openlocfilehash: ea85d57e9af4fdd640733db5dc2fa8b0ab25325c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="448f0-102">Gewusst wie: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="448f0-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="448f0-103">In diesem Beispiel wird ein <xref:System.IO.StreamWriter>-Objekt mit der `My.Computer.FileSystem.OpenTextFileWriter`-Methode geöffnet. Es wird dazu verwendet, eine Zeichenfolge mit der <xref:System.IO.TextWriter.WriteLine%2A>-Methode der <xref:System.IO.StreamWriter>-Klasse in eine Textdatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="448f0-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="448f0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="448f0-104">Example</span></span>  
 <span data-ttu-id="448f0-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="448f0-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="448f0-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="448f0-106">Robust Programming</span></span>  
 <span data-ttu-id="448f0-107">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="448f0-107">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="448f0-108">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="448f0-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="448f0-109">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="448f0-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="448f0-110">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="448f0-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="448f0-111">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="448f0-111">.NET Framework Security</span></span>  
 <span data-ttu-id="448f0-112">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="448f0-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="448f0-113">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="448f0-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="448f0-114">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="448f0-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="448f0-115">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="448f0-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448f0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="448f0-116">See Also</span></span>  
 <span data-ttu-id="448f0-117"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="448f0-117"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="448f0-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="448f0-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="448f0-119">[Vorgehensweise: Lesen aus Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="448f0-119">[How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span></span>  
 [<span data-ttu-id="448f0-120">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="448f0-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

