---
title: 'Vorgehensweise: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: 39c6ad59ad965f566c77f72dd4a97335494d6382
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678524"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="9539d-102">Vorgehensweise: Schreiben von Text in Dateien mit einem StreamWriter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9539d-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="9539d-103">In diesem Beispiel wird ein <xref:System.IO.StreamWriter>-Objekt mit der `My.Computer.FileSystem.OpenTextFileWriter`-Methode geöffnet. Es wird dazu verwendet, eine Zeichenfolge mit der <xref:System.IO.TextWriter.WriteLine%2A>-Methode der <xref:System.IO.StreamWriter>-Klasse in eine Textdatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="9539d-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9539d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9539d-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9539d-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="9539d-105">Robust Programming</span></span>  
 <span data-ttu-id="9539d-106">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="9539d-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9539d-107">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9539d-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9539d-108">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9539d-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9539d-109">Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="9539d-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9539d-110">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9539d-110">.NET Framework Security</span></span>  
 <span data-ttu-id="9539d-111">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9539d-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="9539d-112">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="9539d-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="9539d-113">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="9539d-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="9539d-114">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="9539d-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9539d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9539d-115">See also</span></span>
- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="9539d-116">Vorgehensweise: Lesen aus Textdateien</span><span class="sxs-lookup"><span data-stu-id="9539d-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
- [<span data-ttu-id="9539d-117">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="9539d-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
