---
title: In (generischer Modifizierer)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004867"
---
# <a name="in-generic-modifier-visual-basic"></a>In (generischer Modifizierer) (Visual Basic)

Das Schlüsselwort `In` gibt für generische Typparameter an, dass der Typparameter kontravariant ist.

## <a name="remarks"></a>Hinweise

Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene. Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.

Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Regeln

Sie können das `In`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.
  
Ein Typparameter kann in einer generischen Schnittstelle oder einem generischen Delegaten als kontra Variant deklariert werden, wenn er nur als Typ von Methoden Argumenten verwendet wird und nicht als Methoden Rückgabetyp verwendet wird. `ByRef`-Parameter können nicht kovariant oder Kontra Variant sein.

Kovarianz und Kontra Varianz werden für Verweis Typen unterstützt und für Werttypen nicht unterstützt.

In Visual Basic können Sie Ereignisse nicht in kontra Varianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben. Außerdem können kontra variant-Schnittstellen keine Unterklassen, enumerationsstrukturen oder Strukturen enthalten, aber Sie können über eine Schnittstelle verfügen.

## <a name="behavior"></a>Verhalten

Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren. Da z. b. in .NET Framework 4 in der <xref:System.Collections.Generic.IComparer%601>-Schnittstelle t als kontra Variant-Typ ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs einem Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungs Methoden zu verwenden, wenn `Employee` von `Person` erbt.

Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.

## <a name="example---contravariant-generic-interface"></a>Beispiel: kontra Variante generische Schnittstelle

Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können. Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a>Beispiel: kontra varianter generischer Delegat

Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen. Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Varianz in generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Out](out-generic-modifier.md)
