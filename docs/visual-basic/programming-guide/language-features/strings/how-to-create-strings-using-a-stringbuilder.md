---
title: 'Gewusst wie: Erstellen von Zeichen folgen mithilfe von StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700108"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Gewusst wie: Erstellen von Zeichen folgen mithilfe von StringBuilder in Visual Basic

In diesem Beispiel wird mithilfe der <xref:System.Text.StringBuilder>-Klasse eine lange Zeichenfolge aus vielen kleineren Zeichen folgen erstellt. Die <xref:System.Text.StringBuilder>-Klasse ist effizienter als der `&=`-Operator, um viele Zeichen folgen zu verketten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Instanz der <xref:System.Text.StringBuilder>-Klasse erstellt, 1.000 Zeichen folgen an diese Instanz angefügt und dann die zugehörige Zeichen folgen Darstellung zurückgegeben:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Siehe auch

- [Verwenden der StringBuilder-Klasse](../../../../standard/base-types/stringbuilder.md)
- [&=-Operator](../../../language-reference/operators/and-assignment-operator.md)
- [Zeichenfolgen](index.md)
- [Erstellen neuer Zeichenfolgen](../../../../standard/base-types/creating-new.md)
- [Bearbeiten von Zeichenfolgen](../../../../standard/base-types/manipulating-strings.md)
