---
title: 'Problembehandlung: Lesen aus und Schreiben in Textdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 8af4160d09f39f2622a007aef793173d614a8b44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406624"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="c5d68-102">Problembehandlung: Lesen aus und Schreiben in Textdateien (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5d68-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>

<span data-ttu-id="c5d68-103">Dieses Thema behandelt häufige Probleme beim Arbeiten mit Textdateien und bietet entsprechende Lösungsansätze an.</span><span class="sxs-lookup"><span data-stu-id="c5d68-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="c5d68-104">Häufige Probleme</span><span class="sxs-lookup"><span data-stu-id="c5d68-104">Common problems</span></span>  

 <span data-ttu-id="c5d68-105">Zu den häufigsten Probleme beim Arbeiten mit Textdateien zählen u.a. Sicherheitsausnahmen, Dateicodierungen oder ungültige Pfade.</span><span class="sxs-lookup"><span data-stu-id="c5d68-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="c5d68-106">Sicherheitsausnahmen</span><span class="sxs-lookup"><span data-stu-id="c5d68-106">Security exceptions</span></span>  

 <span data-ttu-id="c5d68-107">Eine <xref:System.Security.SecurityException> wird ausgelöst, wenn ein Sicherheitsfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c5d68-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="c5d68-108">Dies geschieht häufig, wenn dem Benutzer notwendige Berechtigungen fehlen; es kann möglicherweise durch das Hinzufügen von Berechtigungen oder die Arbeit mit Dateien in einem isolierten Speicher behoben werden.</span><span class="sxs-lookup"><span data-stu-id="c5d68-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="c5d68-109">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="c5d68-109">File encodings</span></span>  

 <span data-ttu-id="c5d68-110">Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c5d68-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="c5d68-111">Unerwartete Zeichen in einer Textdatei können aufgrund einer falschen Codierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="c5d68-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="c5d68-112">Für die meisten Dateien ist eine Codierung vielleicht einer anderen vorzuziehen, je nachdem, welche Sprachzeichen sie verarbeiten oder nicht verarbeiten kann. Unicode wird jedoch in der Regel empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c5d68-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="c5d68-113">Weitere Informationen finden Sie unter [Dateicodierungen](file-encodings.md) und <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c5d68-113">For more information, see [File Encodings](file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="c5d68-114">Falsche Pfade</span><span class="sxs-lookup"><span data-stu-id="c5d68-114">Incorrect paths</span></span>  

 <span data-ttu-id="c5d68-115">Beim Analysieren von Dateipfaden, insbesondere bei relativen Pfaden, ist es einfach, die falschen Daten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c5d68-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="c5d68-116">Viele Probleme können korrigiert werden, indem Sie sicherstellen, dass Sie den richtigen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="c5d68-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="c5d68-117">Weitere Informationen finden Sie unter [Vorgehensweise: Analysieren von Dateipfaden](how-to-parse-file-paths.md).</span><span class="sxs-lookup"><span data-stu-id="c5d68-117">For more information, see [How to: Parse File Paths](how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d68-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5d68-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="c5d68-119">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="c5d68-119">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="c5d68-120">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="c5d68-120">Writing to Files</span></span>](writing-to-files.md)
- [<span data-ttu-id="c5d68-121">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="c5d68-121">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
