---
title: 'Gewusst wie: Erstellen von Zeichenfolgen mit einem StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645327"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Gewusst wie: Erstellen von Zeichenfolgen mit einem StringBuilder in Visual Basic

In diesem Beispiel wird eine lange Zeichenfolge <xref:System.Text.StringBuilder> aus vielen kleineren Zeichenfolgen mithilfe der Klasse erstellt. Die <xref:System.Text.StringBuilder> Klasse ist effizienter `&=` als der Operator, um viele Zeichenfolgen zu verketten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird <xref:System.Text.StringBuilder> eine Instanz der Klasse erstellt, 1.000 Zeichenfolgen an diese Instanz angehängt und dann ihre Zeichenfolgendarstellung zurückgegeben:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Siehe auch

- [Verwenden der StringBuilder-Klasse](../../../../standard/base-types/stringbuilder.md)
- [&= Operator](../../../language-reference/operators/and-assignment-operator.md)
- [Zeichenfolgen](index.md)
- [Erstellen neuer Zeichenfolgen](../../../../standard/base-types/creating-new.md)
- [Bearbeiten von Zeichenfolgen](../../../../standard/base-types/best-practices-strings.md)
