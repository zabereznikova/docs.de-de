---
title: "Gewusst wie: Schreiben in Binärdateien in Visual Basic"
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
- files, binary access
- WriteAllBytes method
- binary files, writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
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
ms.openlocfilehash: ae6f275dd86a53c6b6251feb08210a775adba0b0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="efb49-102">Gewusst wie: Schreiben in Binärdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efb49-102">How to: Write to Binary Files in Visual Basic</span></span>
<span data-ttu-id="efb49-103">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>-Methode schreibt Daten in eine Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="efb49-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="efb49-104">Wenn der `append`-Parameter `True` ist, fügt er die Daten an die Datei an. Andernfalls werden die Daten in der Datei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="efb49-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>  
  
 <span data-ttu-id="efb49-105">Wenn der angegebene Pfad mit dem Dateinamen nicht zulässig ist, wird eine <xref:System.IO.DirectoryNotFoundException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="efb49-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="efb49-106">Wenn der Pfad zulässig ist, die Datei aber nicht existiert, wird die Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="efb49-106">If the path is valid but the file does not exist, the file will be created.</span></span>  
  
### <a name="to-write-to-a-binary-file"></a><span data-ttu-id="efb49-107">Schreiben in eine Binärdatei</span><span class="sxs-lookup"><span data-stu-id="efb49-107">To write to a binary file</span></span>  
  
-   <span data-ttu-id="efb49-108">Verwenden Sie die `WriteAllBytes`-Methode, die den Dateipfad und -namen und die zu schreibenden Bytes bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="efb49-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="efb49-109">In diesem Beispiel wird das Datenarray `CustomerData` an die Datei `CollectedData.dat` angefügt.</span><span class="sxs-lookup"><span data-stu-id="efb49-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>  
  
     <span data-ttu-id="efb49-110">[!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="efb49-110">[!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="efb49-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="efb49-111">Robust Programming</span></span>  
 <span data-ttu-id="efb49-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="efb49-112">The following conditions may create an exception:</span></span>  
  
-   <span data-ttu-id="efb49-113">Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0 (null), der Pfad enthält nur Leerzeichen, oder er enthält ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="efb49-113">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="efb49-114">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-114">(<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="efb49-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="efb49-116">`File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-116">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="efb49-117">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-117">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="efb49-118">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="efb49-119">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="efb49-120">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="efb49-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb49-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efb49-121">See Also</span></span>  
 <span data-ttu-id="efb49-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span><span class="sxs-lookup"><span data-stu-id="efb49-122"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span></span>   
 [<span data-ttu-id="efb49-123">Gewusst wie: Schreiben von Text in Dateien</span><span class="sxs-lookup"><span data-stu-id="efb49-123">How to: Write Text to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)

