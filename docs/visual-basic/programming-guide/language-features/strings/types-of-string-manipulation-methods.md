---
title: Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 349cfdb3e31225f6aeba90ac29aa1c66e37c7e11
ms.lasthandoff: 03/13/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic
Es gibt verschiedene Zeichenfolgen zu analysieren. Einige Methoden sind Teil der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Sprache und andere sind Bestandteil der `String` Klasse.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic-Sprache und .NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Methoden werden als inhärente Funktionen der Sprache verwendet. Sie können ohne Qualifizierung in Ihrem Code verwendet werden. Das folgende Beispiel zeigt die standardmäßige Verwendung für eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolgenmanipulation Befehl:  
  
 [!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 In diesem Beispiel die `Mid` Funktion führt eine direkte Operation auf `aString` und weist den Wert `bString`.  
  
 Eine Liste der Visual Basic-Zeichenfolgenbearbeitungsmethoden, finden Sie unter [Zeichenfolgenbearbeitung: Zusammenfassung](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Freigegebene Methoden und Instanzmethoden  
 Kann auch das Bearbeiten von Zeichenfolgen mit den Methoden von der `String` Klasse. Es gibt zwei Arten von Methoden in `String`: *freigegebenen* Methoden und *Instanz* Methoden.  
  
#### <a name="shared-methods"></a>Freigegebene Methoden  
 Eine freigegebene Methode ist eine Methode, die vom herrührt der `String` selbst dar und erfordert eine Instanz der Klasse. Diese Methoden können mit dem Namen der Klasse qualifiziert werden (`String`) anstatt mit einer Instanz von der `String` Klasse. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings&#45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 Im vorherigen Beispiel ist die <xref:System.String.Copy%2A?displayProperty=fullName>Methode ist eine statische Methode, die auf einen Ausdruck angewendet wird und weist den resultierenden Wert `bString`.</xref:System.String.Copy%2A?displayProperty=fullName>  
  
#### <a name="instance-methods"></a>Instanzmethoden  
 Instanzmethoden, im Gegensatz dazu entstammen einer bestimmten Instanz von `String` und müssen mit dem Instanznamen qualifiziert werden. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings&#46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 In diesem Beispiel die <xref:System.String.Substring%2A?displayProperty=fullName>Methode ist eine Methode der Instanz von `String` (d. h. `aString`).</xref:System.String.Substring%2A?displayProperty=fullName> Sie führt eine Operation auf `aString` und weist diesen Wert `bString`.  
  
 Weitere Informationen finden Sie in der Dokumentation für die <xref:System.String>Klasse.</xref:System.String>  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
