---
title: Verschiedene Typen von Methoden zur Zeichenfolgenbearbeitung
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: c44f02880858b8a9fc1f0e70c3226623d05baa3a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072469"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic

Es gibt verschiedene Möglichkeiten, ihre Zeichen folgen zu analysieren und zu bearbeiten. Einige der Methoden sind Teil der Visual Basic Sprache, andere sind in der- `String` Klasse enthalten.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic Sprache und .NET Framework  

 Visual Basic Methoden werden als inhärente Funktionen der Sprache verwendet. Sie können ohne Qualifizierung in Ihrem Code verwendet werden. Das folgende Beispiel zeigt die typische Verwendung eines Befehls zur Zeichen folgen Bearbeitung (Visual Basic):  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 In diesem Beispiel führt die `Mid` -Funktion einen direkten Vorgang für aus `aString` und weist den Wert zu `bString` .  
  
 Eine Liste der Methoden zur Bearbeitung von Visual Basic Zeichen folgen finden Sie unter [Zusammenfassung der Zeichen folgen Bearbeitung](../../../language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Freigegebene Methoden und Instanzmethoden  

 Sie können Zeichen folgen auch mit den Methoden der- `String` Klasse bearbeiten. Es gibt zwei Arten von Methoden in `String` : frei *gegebene* Methoden und *Instanzmethoden* .  
  
#### <a name="shared-methods"></a>Freigegebene Methoden  

 Eine freigegebene Methode ist eine Methode, die sich aus der `String` Klasse selbst ergibt und keine Instanz dieser Klasse erfordert. Diese Methoden können `String` anstelle einer Instanz der-Klasse mit dem Namen der Klasse () qualifiziert werden `String` . Beispiel:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 Im vorherigen Beispiel ist die- <xref:System.String.Copy%2A?displayProperty=nameWithType> Methode eine statische-Methode, die auf einen Ausdruck angewendet wird, den Sie erhält, und weist den resultierenden Wert zu `bString` .  
  
#### <a name="instance-methods"></a>Instanzmethoden  

 Instanzmethoden werden dagegen von einer bestimmten Instanz von abgeleitet `String` und müssen mit dem Instanznamen qualifiziert werden. Beispiel:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 In diesem Beispiel ist die- <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode eine Methode der-Instanz `String` (d. h `aString` .). Er führt einen Vorgang für aus `aString` und weist diesen Wert zu `bString` .  
  
 Weitere Informationen finden Sie in der Dokumentation für die- <xref:System.String> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
