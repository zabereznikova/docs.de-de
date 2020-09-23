---
title: 'Vorgehensweise: Konvertieren eines Arrays von Bytes in eine Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 49c1e454b845bd545d7a8dccb3a3d9a39ff2db21
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085658"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="9948a-102">Gewusst wie: Konvertieren eines Bytearrays in eine Zeichenfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9948a-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>

<span data-ttu-id="9948a-103">In diesem Thema wird gezeigt, wie die Bytes aus einem Bytearray in eine Zeichenfolge konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="9948a-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9948a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9948a-104">Example</span></span>  

 <span data-ttu-id="9948a-105">In diesem Beispiel wird die- <xref:System.Text.Encoding.GetString%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> Encoding-Klasse verwendet, um alle Bytes aus einem Bytearray in eine Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9948a-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="9948a-106">Sie können aus mehreren Codierungsoptionen auswählen, um ein Bytearray in eine Zeichenfolge zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="9948a-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="9948a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="9948a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit der Big-Endian-Byte Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="9948a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="9948a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit der Little-Endian-Byte Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="9948a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format unter Verwendung der Little-Endian-Byte Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="9948a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="9948a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.</span><span class="sxs-lookup"><span data-stu-id="9948a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9948a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9948a-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="9948a-115">Gewusst wie: Konvertieren von Zeichenfolgen in ein Bytearray in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9948a-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](how-to-convert-strings-into-an-array-of-bytes.md)
