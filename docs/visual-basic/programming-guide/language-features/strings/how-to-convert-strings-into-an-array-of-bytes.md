---
title: 'Vorgehensweise: Konvertieren von Zeichenfolgen in ein Bytearray'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: d9a5a329a82555e66a391fd93005634106569232
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071182"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Gewusst wie: Konvertieren von Zeichenfolgen in ein Bytearray in Visual Basic

In diesem Thema wird gezeigt, wie eine Zeichenfolge in ein Bytearray konvertiert wird.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird die- <xref:System.Text.Encoding.GetBytes%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> Encoding-Klasse verwendet, um eine Zeichenfolge in ein Bytearray zu konvertieren.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 Sie können zwischen mehreren Codierungsoptionen wählen, um eine Zeichenfolge in ein Bytearray zu konvertieren:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) ab.  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit der Big-Endian-Byte Reihenfolge ab.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit der Little-Endian-Byte Reihenfolge ab.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format unter Verwendung der Little-Endian-Byte Reihenfolge ab.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Gewusst wie: Konvertieren eines Bytearrays in eine Zeichenfolge in Visual Basic](how-to-convert-an-array-of-bytes-into-a-string.md)
