---
title: 'Gewusst wie: Suchen innerhalb einer Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348422"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)

Dieser Artikel zeigt ein Beispiel für die Suche in einer Zeichenfolge in Visual Basic.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die <xref:System.String.IndexOf%2A>-Methode für ein <xref:System.String> Objekt aufgerufen, um den Index des ersten Vorkommens einer Teil Zeichenfolge zu melden:

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a>Stabile Programmierung

Die <xref:System.String.IndexOf%2A>-Methode gibt den Speicherort des ersten Zeichens des ersten Vorkommens der Teil Zeichenfolge zurück. Der Index ist 0-basiert, was bedeutet, dass das erste Zeichen einer Zeichenfolge einen Index von 0 aufweist.

Wenn die Teil Zeichenfolge von <xref:System.String.IndexOf%2A> nicht gefunden wird, wird-1 zurückgegeben.

Bei der <xref:System.String.IndexOf%2A>-Methode wird die Groß-/Kleinschreibung beachtet und die aktuelle Kultur verwendet.

Um die optimale Fehler Steuerung zu erzielen, sollten Sie die Zeichen folgen Suche in den `Try`-Block eines [try... Catch... Schließlich ist die Anweisungs](../../../language-reference/statements/try-catch-finally-statement.md) Erstellung.

## <a name="see-also"></a>Siehe auch

- <xref:System.String.IndexOf%2A>
- [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md)
- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
- [Zeichenfolgen](index.md)
