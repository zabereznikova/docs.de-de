---
title: Dateicodierungen
ms.date: 07/20/2015
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
ms.openlocfilehash: 52770187568d0ba0f54ec36ee2c3d754a9b4d9a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348891"
---
# <a name="file-encodings-visual-basic"></a><span data-ttu-id="10843-102">Dateicodierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10843-102">File Encodings (Visual Basic)</span></span>

<span data-ttu-id="10843-103">Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10843-103">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="10843-104">Eine Codierung ist womöglich einer anderen vorzuziehen, je nachdem, welche Sprachzeichen sie verarbeiten oder nicht verarbeiten kann. Unicode wird jedoch in der Regel empfohlen.</span><span class="sxs-lookup"><span data-stu-id="10843-104">One encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span>

<span data-ttu-id="10843-105">Nicht ordnungsgemäß übereinstimmende Dateicodierungen führen möglicherweise beim Lesen aus oder Schreiben in Dateien zu Ausnahmen oder falschen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="10843-105">When reading from or writing to files, improperly matching file encodings may result in exceptions or incorrect results.</span></span>

## <a name="types-of-encodings"></a><span data-ttu-id="10843-106">Typen von Codierungen</span><span class="sxs-lookup"><span data-stu-id="10843-106">Types of Encodings</span></span>

<span data-ttu-id="10843-107">Unicode ist die perfekte Codierung beim Arbeiten mit Dateien.</span><span class="sxs-lookup"><span data-stu-id="10843-107">Unicode is the preferred encoding when working with files.</span></span> <span data-ttu-id="10843-108">Unicode ist eine globale Standardzeichencodierung, die 16-Bit-Codewerte verwendet, um alle Zeichen darzustellen, die in der modernen Computertechnik verwendet werden, einschließlich technischer Symbole und Sonderzeichen, die in der Veröffentlichung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10843-108">Unicode is a worldwide character-encoding standard that uses 16-bit code values to represent all the characters used in modern computing, including technical symbols and special characters used in publishing.</span></span>

<span data-ttu-id="10843-109">Frühere Standardzeichencodierungen bestanden aus traditionellen Zeichensätzen, z.B. den Windows ANSI-Zeichensatz, der einen 8-Bit-Codewert oder Kombinationen von 8-Bit-Werten verwendet, um die Zeichen darzustellen, die in einer bestimmten Sprache oder geografischen Region verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10843-109">Previous character-encoding standards consisted of traditional character sets, such as the Windows ANSI character set that uses 8-bit code values, or combinations of 8-bit values, to represent the characters used in a specific language or geographical region.</span></span>

## <a name="encoding-class"></a><span data-ttu-id="10843-110">Codierungsklasse</span><span class="sxs-lookup"><span data-stu-id="10843-110">Encoding Class</span></span>

<span data-ttu-id="10843-111">Die Klasse <xref:System.Text.Encoding> stellt eine Zeichencodierung dar.</span><span class="sxs-lookup"><span data-stu-id="10843-111">The <xref:System.Text.Encoding> class represents a character encoding.</span></span> <span data-ttu-id="10843-112">Diese Tabelle führt den verfügbaren Typ der Codierungen auf und beschreibt diesen.</span><span class="sxs-lookup"><span data-stu-id="10843-112">This table lists the type of encodings available and describes each.</span></span>

|<span data-ttu-id="10843-113">Name</span><span class="sxs-lookup"><span data-stu-id="10843-113">Name</span></span>|<span data-ttu-id="10843-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10843-114">Description</span></span>|
|---|---|
|<xref:System.Text.ASCIIEncoding>|<span data-ttu-id="10843-115">Stellt eine ASCII-Zeichencodierung von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="10843-115">Represents an ASCII character encoding of Unicode characters.</span></span>|
|<xref:System.Text.UnicodeEncoding>|<span data-ttu-id="10843-116">Stellt eine UTF-16-Codierung von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="10843-116">Represents a UTF-16 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF32Encoding>|<span data-ttu-id="10843-117">Stellt eine UTF-32-Codierung von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="10843-117">Represents a UTF-32 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF7Encoding>|<span data-ttu-id="10843-118">Stellt eine UTF-7-Codierung von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="10843-118">Represents a UTF-7 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF8Encoding>|<span data-ttu-id="10843-119">Stellt eine UTF-8-Codierung von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="10843-119">Represents a UTF-8 encoding of Unicode characters.</span></span>|

## <a name="see-also"></a><span data-ttu-id="10843-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10843-120">See also</span></span>

- [<span data-ttu-id="10843-121">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="10843-121">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="10843-122">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="10843-122">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
