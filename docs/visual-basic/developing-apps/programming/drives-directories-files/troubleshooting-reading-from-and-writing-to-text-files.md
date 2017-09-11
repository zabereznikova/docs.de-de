---
title: 'Problembehandlung: Lesen aus und Schreiben in Textdateien (Visual Basic)'
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
- troubleshooting file I/O
- writing text to files, troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files, troubleshooting
- reading text files, troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
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
ms.openlocfilehash: 7f1d26df53445ee9711ebb2840071d2560c5380d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="d9819-102">Problembehandlung: Lesen aus und Schreiben in Textdateien (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9819-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>
<span data-ttu-id="d9819-103">Dieses Thema behandelt häufige Probleme beim Arbeiten mit Textdateien und bietet entsprechende Lösungsansätze an.</span><span class="sxs-lookup"><span data-stu-id="d9819-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="d9819-104">Häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="d9819-104">Common problems</span></span>  
 <span data-ttu-id="d9819-105">Zu den häufigsten Probleme beim Arbeiten mit Textdateien zählen u.a. Sicherheitsausnahmen, Dateicodierungen oder ungültige Pfade.</span><span class="sxs-lookup"><span data-stu-id="d9819-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="d9819-106">Sicherheitsausnahmen</span><span class="sxs-lookup"><span data-stu-id="d9819-106">Security exceptions</span></span>  
 <span data-ttu-id="d9819-107">Eine <xref:System.Security.SecurityException> wird ausgelöst, wenn ein Sicherheitsfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="d9819-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="d9819-108">Dies geschieht häufig, wenn dem Benutzer notwendige Berechtigungen fehlen; es kann möglicherweise durch das Hinzufügen von Berechtigungen oder die Arbeit mit Dateien in einem isolierten Speicher behoben werden.</span><span class="sxs-lookup"><span data-stu-id="d9819-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="d9819-109">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="d9819-109">File encodings</span></span>  
 <span data-ttu-id="d9819-110">Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d9819-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="d9819-111">Unerwartete Zeichen in einer Textdatei können aufgrund einer falschen Codierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="d9819-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="d9819-112">Für die meisten Dateien ist eine Codierung vielleicht einer anderen vorzuziehen, je nachdem, welche Sprachzeichen sie verarbeiten oder nicht verarbeiten kann. Unicode wird jedoch in der Regel empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d9819-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="d9819-113">Weitere Informationen finden Sie unter [Dateicodierungen](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) und <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d9819-113">For more information, see [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="d9819-114">Falsche Pfade</span><span class="sxs-lookup"><span data-stu-id="d9819-114">Incorrect paths</span></span>  
 <span data-ttu-id="d9819-115">Beim Analysieren von Dateipfaden, insbesondere bei relativen Pfaden, ist es einfach, die falschen Daten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d9819-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="d9819-116">Viele Probleme können korrigiert werden, indem Sie sicherstellen, dass Sie den richtigen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="d9819-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="d9819-117">Weitere Informationen finden Sie unter [Vorgehensweise: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span><span class="sxs-lookup"><span data-stu-id="d9819-117">For more information, see [How to: Parse File Paths](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9819-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9819-118">See also</span></span>  
 <span data-ttu-id="d9819-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="d9819-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="d9819-120">[Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span><span class="sxs-lookup"><span data-stu-id="d9819-120">[Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span></span>  
 <span data-ttu-id="d9819-121">[Schreiben in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md) </span><span class="sxs-lookup"><span data-stu-id="d9819-121">[Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md) </span></span>  
 [<span data-ttu-id="d9819-122">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="d9819-122">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)

