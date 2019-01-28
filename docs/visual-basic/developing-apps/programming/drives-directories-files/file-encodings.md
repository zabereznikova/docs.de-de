---
title: Dateicodierungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
ms.openlocfilehash: f7ccd47b8778aa3a374ee102b39038e8df475e9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731919"
---
# <a name="file-encodings-visual-basic"></a>Dateicodierungen (Visual Basic)
Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden. Eine Codierung ist womöglich einer anderen vorzuziehen, je nachdem, welche Sprachzeichen sie verarbeiten oder nicht verarbeiten kann. Unicode wird jedoch in der Regel empfohlen.  
  
 Nicht ordnungsgemäß übereinstimmende Dateicodierungen führen möglicherweise beim Lesen aus oder Schreiben in Dateien zu Ausnahmen oder falschen Ergebnissen.  
  
## <a name="types-of-encodings"></a>Typen von Codierungen  
 Unicode ist die perfekte Codierung beim Arbeiten mit Dateien. Unicode ist eine globale Standardzeichencodierung, die 16-Bit-Codewerte verwendet, um alle Zeichen darzustellen, die in der modernen Computertechnik verwendet werden, einschließlich technischer Symbole und Sonderzeichen, die in der Veröffentlichung verwendet werden.  
  
 Frühere Standardzeichencodierungen bestanden aus traditionellen Zeichensätzen, z.B. den Windows ANSI-Zeichensatz, der einen 8-Bit-Codewert oder Kombinationen von 8-Bit-Werten verwendet, um die Zeichen darzustellen, die in einer bestimmten Sprache oder geografischen Region verwendet werden.  
  
## <a name="encoding-class"></a>Codierungsklasse  
 Die Klasse <xref:System.Text.Encoding> stellt eine Zeichencodierung dar. Diese Tabelle führt den verfügbaren Typ der Codierungen auf und beschreibt diesen.  
  
|name|Beschreibung|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|Stellt eine ASCII-Zeichencodierung von Unicode-Zeichen dar.|  
|<xref:System.Text.UnicodeEncoding>|Stellt eine UTF-16-Codierung von Unicode-Zeichen dar.|  
|<xref:System.Text.UTF32Encoding>|Stellt eine UTF-32-Codierung von Unicode-Zeichen dar.|  
|<xref:System.Text.UTF7Encoding>|Stellt eine UTF-7-Codierung von Unicode-Zeichen dar.|  
|<xref:System.Text.UTF8Encoding>|Stellt eine UTF-8-Codierung von Unicode-Zeichen dar.|  
  
## <a name="see-also"></a>Siehe auch
- [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Schreiben in Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
