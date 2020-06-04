---
title: Out (generischer Modifizierer)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 28ae7d6fd51170aa822072fc2f5357443f51a353
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392092"
---
# <a name="out-generic-modifier-visual-basic"></a>Out (generischer Modifizierer) (Visual Basic)

Bei generischen Typparametern `Out` gibt das Schlüsselwort an, dass der Typ kovariant ist.

## <a name="remarks"></a>Bemerkungen

Kovarianz ermöglicht Ihnen die Verwendung eines stärker abgeleiteten Typs als durch den generischen Parameter angegeben. Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.

Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Regeln

Sie können das `Out`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.

In einer generischen Schnittstelle kann ein Typparameter als kovariant deklariert werden, wenn er die folgenden Bedingungen erfüllt:

- Der Typparameter wird nur als Rückgabetyp von Schnittstellenmethoden, und nicht als Typ von Methodenargumenten verwendet.

    > [!NOTE]
    > Es gibt allerdings eine Ausnahme zu dieser Regel. Wenn Sie in einer kovarianten Schnittstelle einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für diesen Delegaten verwenden. Weitere Informationen über kovariante und kontravariante generische Delegate finden Sie unter [Varianz in Delegaten](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- Der Typparameter wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.

In einem generischen Delegaten kann ein Typparameter als kovariant deklariert werden, wenn er nur als Methoden Rückgabetyp verwendet und nicht für Methodenargumente verwendet wird.

Kovarianz und Kontravarianz werden für Verweistypen unterstützt, aber nicht für Werttypen.

In Visual Basic können Sie Ereignisse nicht in kovarianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben. Außerdem können kovariante Schnittstellen keine Unterklassen, enumerationsstrukturen oder Strukturen enthalten, aber Sie können über eine Schnittstelle verfügen.

## <a name="behavior"></a>Verhalten

Die Methoden einer Schnittstelle, die einen kovarianten Typparameter hat, können mehr abgeleitete Typen als durch den Typparameter angegeben zurückgeben. Da z.B. in .NET Framework 4 Typ T in <xref:System.Collections.Generic.IEnumerable%601> kovariant ist, können Sie ein Objekt des `IEnumerable(Of String)`-Typs an ein Objekt des `IEnumerable(Of Object)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden.

Ein kovarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem stärker abgeleiteten generischen Typparameter.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie eine kovariante generische Schnittstelle deklarieren, erweitern und implementieren. Es wird auch gezeigt, wie eine implizite Konvertierung für Klassen verwendet wird, die eine kovariante Schnittstelle implementieren.

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren, instanziieren und aufrufen. Außerdem wird gezeigt, wie Sie die implizite Konvertierung für Delegattypen verwenden können.

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a>Weitere Informationen

- [Abweichungen bei generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Geben Sie in](in-generic-modifier.md)
