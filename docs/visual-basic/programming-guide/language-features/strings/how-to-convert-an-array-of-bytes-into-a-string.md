---
title: 'Vorgehensweise: Konvertiert ein Array von Bytes in eine Zeichenfolge in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 50acfdbfb9b093f719928f68d90a40f09da5ade5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665364"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Vorgehensweise: Konvertiert ein Array von Bytes in eine Zeichenfolge in Visual Basic
In diesem Thema zeigt, wie die Bytes aus einem Bytearray in eine Zeichenfolge konvertiert wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Text.Encoding.GetString%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding-Klasse, um alle Bytes aus einem Bytearray in eine Zeichenfolge konvertiert.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Sie können aus mehreren Codierungsoptionen ein Bytearray in eine Zeichenfolge konvertiert:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) ab.  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit big-Endian-Bytereihenfolge ab.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit little-Endian-Bytereihenfolge ab.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format mit little-Endian-Bytereihenfolge ab.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Vorgehensweise: Konvertieren von Zeichenfolgen in ein Array von Bytes in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
