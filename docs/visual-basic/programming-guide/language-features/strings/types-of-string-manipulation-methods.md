---
title: Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648693"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
Es gibt verschiedene Möglichkeiten, analysieren und Bearbeiten von Zeichenfolgen. Einige der Methoden sind Teil der Sprache Visual Basic und andere sind Bestandteil der `String` Klasse.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Sprache Visual Basic und .NET Framework  
 Visual Basic-Methoden werden als inhärenten Funktionen der Sprache verwendet. Sie können ohne Qualifizierung in Ihrem Code verwendet werden. Das folgende Beispiel zeigt die typische Verwendung eines Visual Basic zeichenfolgenbearbeitung Befehls:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 In diesem Beispiel wird die `Mid` Funktion führt eine direkte Operation auf `aString` und weist den Wert `bString`.  
  
 Eine Liste der Visual Basic-Zeichenfolgenbearbeitungsmethoden, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Freigegebener Methoden und Instanzenmethoden  
 Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden von der `String` Klasse. Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.  
  
#### <a name="shared-methods"></a>Shared-Methoden  
 Eine freigegebene Methode ist eine Methode, die aus resultiert der `String` selbst dar und erfordert eine Instanz dieser Klasse funktioniert nicht. Diese Methoden können mit dem Namen der Klasse qualifiziert werden (`String`) anstatt mit einer Instanz von der `String` Klasse. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 Im vorherigen Beispiel der <xref:System.String.Copy%2A?displayProperty=nameWithType> Methode ist eine statische Methode nimmt einen Ausdruck als Argument fungiert es erhält und weist den resultierenden Wert an `bString`.  
  
#### <a name="instance-methods"></a>Instanzmethoden  
 Instanzmethoden, entstammen, im Gegensatz dazu eine bestimmte Instanz des `String` und muss mit dem Instanznamen qualifiziert sein. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 In diesem Beispiel wird die <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode ist eine Methode der Instanz von `String` (d. h. `aString`). Es führt eine Operation auf `aString` und weist diesen Wert `bString`.  
  
 Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String> Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
