---
title: Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938267"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
Es gibt mehrere Möglichkeiten, um zu analysieren und Bearbeiten von Zeichenfolgen. Einige der Methoden sind Teil der Visual Basic-Sprache und andere sind Bestandteil der `String` Klasse.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic-Sprache und .NET Framework  
 Visual Basic-Methoden werden als enthaltenen Funktionen der Sprache verwendet. Sie können ohne Qualifikation in Ihrem Code verwendet werden. Das folgende Beispiel zeigt die typische Verwendung von einem Visual Basic-zeichenfolgenbearbeitung Befehl:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 In diesem Beispiel die `Mid` Funktion führt eine direkte Operation für `aString` und weist den Wert `bString`.  
  
 Eine Liste der Methoden zur zeichenfolgenbearbeitung Visual Basic, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Freigegebener Methoden und Instanzmethoden  
 Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden der `String` Klasse. Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.  
  
#### <a name="shared-methods"></a>Freigegebene Methoden  
 Eine freigegebene Methode ist eine Methode, die vom herrührt der `String` selbst und erfordert eine Instanz dieser Klasse funktioniert nicht. Diese Methoden können mit dem Namen der Klasse qualifiziert sein (`String`) statt mit einer Instanz von der `String` Klasse. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 Im vorherigen Beispiel das <xref:System.String.Copy%2A?displayProperty=nameWithType> Methode ist eine statische Methode, die auf einen Ausdruck angewendet wird und weist den resultierenden Wert an `bString`.  
  
#### <a name="instance-methods"></a>Instanzmethoden  
 Stem-Instanzenmethoden, im Gegensatz dazu, von einer bestimmten Instanz von `String` und muss mit dem Namen qualifiziert werden. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 In diesem Beispiel die <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode ist eine Methode der Instanz von `String` (d. h. `aString`). Er führt einen Vorgang auf `aString` und weist diesen Wert `bString`.  
  
 Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
