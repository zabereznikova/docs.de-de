---
title: 'Vorgehensweise: Konvertiert ein Array von Bytes in eine Zeichenfolge in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: cd091d743b04ef9d9709bde2b5a1205f3d7ae292
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979508"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="fdeb3-102">Vorgehensweise: Konvertiert ein Array von Bytes in eine Zeichenfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdeb3-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="fdeb3-103">In diesem Thema zeigt, wie die Bytes aus einem Bytearray in eine Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdeb3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdeb3-104">Example</span></span>  
 <span data-ttu-id="fdeb3-105">Dieses Beispiel verwendet die <xref:System.Text.Encoding.GetString%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding-Klasse, um alle Bytes aus einem Bytearray in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="fdeb3-106">Sie können aus mehreren Codierungsoptionen ein Bytearray in eine Zeichenfolge konvertiert:</span><span class="sxs-lookup"><span data-stu-id="fdeb3-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
-   <span data-ttu-id="fdeb3-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="fdeb3-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit big-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="fdeb3-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="fdeb3-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit little-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="fdeb3-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format mit little-Endian-Bytereihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="fdeb3-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="fdeb3-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.</span><span class="sxs-lookup"><span data-stu-id="fdeb3-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdeb3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdeb3-114">See also</span></span>
- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="fdeb3-115">Vorgehensweise: Konvertieren von Zeichenfolgen in ein Array von Bytes in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdeb3-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
