---
title: 'Gewusst wie: Konvertieren eines Bytearrays in eine Zeichenfolge in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4133109ef334c7e87884deb7db963db3291da1d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Gewusst wie: Konvertieren eines Bytearrays in eine Zeichenfolge in Visual Basic
In diesem Thema wird gezeigt, wie die Bytes aus einem Bytearray in eine Zeichenfolge zu konvertieren.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Text.Encoding.GetString%2A> Methode der <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding-Klasse, um alle Bytes aus einem Bytearray in eine Zeichenfolge zu konvertieren.  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 Sie können aus mehreren Codierungsoptionen ein Bytearray in eine Zeichenfolge zu konvertieren:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ruft eine Codierung für den ASCII-Zeichensatz (7-Bit) festlegen.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit big-Endian-Bytereihenfolge ab.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ruft eine Codierung für die aktuelle ANSI-Codepage des Systems ab.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-16-Format mit little-Endian-Bytereihenfolge ab.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-32-Format mit little-Endian-Bytereihenfolge ab.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-7-Format ab.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ruft eine Codierung für das UTF-8-Format ab.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetString%2A>  
 [Vorgehensweise: Konvertieren von Zeichenfolgen in ein Array von Bytes in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
