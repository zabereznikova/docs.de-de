---
title: 'Gewusst wie: Schreiben in Binärdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 72d019f5f49868bd84d0507535e8ebc547b50e25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334429"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="39bdb-102">Gewusst wie: Schreiben in Binärdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39bdb-102">How to: Write to Binary Files in Visual Basic</span></span>

<span data-ttu-id="39bdb-103">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>-Methode schreibt Daten in eine Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="39bdb-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="39bdb-104">Wenn der `append`-Parameter `True` ist, fügt er die Daten an die Datei an. Andernfalls werden die Daten in der Datei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="39bdb-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>

<span data-ttu-id="39bdb-105">Wenn der angegebene Pfad mit dem Dateinamen nicht zulässig ist, wird eine <xref:System.IO.DirectoryNotFoundException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39bdb-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="39bdb-106">Wenn der Pfad zulässig ist, die Datei aber nicht existiert, wird die Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="39bdb-106">If the path is valid but the file does not exist, the file will be created.</span></span>

## <a name="to-write-to-a-binary-file"></a><span data-ttu-id="39bdb-107">Schreiben in eine Binärdatei</span><span class="sxs-lookup"><span data-stu-id="39bdb-107">To write to a binary file</span></span>

<span data-ttu-id="39bdb-108">Verwenden Sie die `WriteAllBytes`-Methode, die den Dateipfad und -namen und die zu schreibenden Bytes bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="39bdb-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="39bdb-109">In diesem Beispiel wird das Datenarray `CustomerData` an die Datei `CollectedData.dat` angefügt.</span><span class="sxs-lookup"><span data-stu-id="39bdb-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a><span data-ttu-id="39bdb-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="39bdb-110">Robust Programming</span></span>

<span data-ttu-id="39bdb-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="39bdb-111">The following conditions may create an exception:</span></span>

- <span data-ttu-id="39bdb-112">Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0 (null), der Pfad enthält nur Leerzeichen, oder er enthält ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="39bdb-112">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="39bdb-113">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-113">(<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="39bdb-114">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="39bdb-115">`File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-115">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="39bdb-116">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-116">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="39bdb-117">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="39bdb-118">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-118">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="39bdb-119">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="39bdb-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="39bdb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39bdb-120">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="39bdb-121">Gewusst wie: Schreiben von Text in Dateien</span><span class="sxs-lookup"><span data-stu-id="39bdb-121">How to: Write Text to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
