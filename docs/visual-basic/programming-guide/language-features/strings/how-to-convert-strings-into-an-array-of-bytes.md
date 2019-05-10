---
title: 'Vorgehensweise: Konvertieren von Zeichenfolgen in ein Array von Bytes in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 786065fde9814d31ac36b56e1455d5b1685122ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665356"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="03527-102">Vorgehensweise: Konvertieren von Zeichenfolgen in ein Array von Bytes in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="03527-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="03527-103">In diesem Thema veranschaulicht das Konvertieren einer Zeichenfolge in ein Array von Bytes.</span><span class="sxs-lookup"><span data-stu-id="03527-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03527-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03527-104">Example</span></span>  
 <span data-ttu-id="03527-105">Dieses Beispiel verwendet die <xref:System.Text.Encoding.GetBytes%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> Codierungsklasse zum Konvertieren einer Zeichenfolge in ein Array von Bytes.</span><span class="sxs-lookup"><span data-stu-id="03527-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="03527-106">Sie können über mehrere Optionen zum Konvertieren einer Zeichenfolge in ein Bytearray:</span><span class="sxs-lookup"><span data-stu-id="03527-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="03527-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) ab.</span><span class="sxs-lookup"><span data-stu-id="03527-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="03527-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit big-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="03527-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="03527-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.</span><span class="sxs-lookup"><span data-stu-id="03527-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="03527-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit little-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="03527-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="03527-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format mit little-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="03527-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="03527-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.</span><span class="sxs-lookup"><span data-stu-id="03527-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="03527-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.</span><span class="sxs-lookup"><span data-stu-id="03527-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03527-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03527-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="03527-115">Vorgehensweise: Konvertiert ein Array von Bytes in eine Zeichenfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="03527-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
