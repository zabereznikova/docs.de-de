---
title: Out (generischer Modifizierer) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: d9e7f3f97657a1d7de2a53502e99721f0e96a15f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977330"
---
# <a name="out-generic-modifier-visual-basic"></a>Out (generischer Modifizierer) (Visual Basic)
Für generische Typparameter der `Out` -Schlüsselwort Gibt an, dass der Typ kovariant ist.  
  
## <a name="remarks"></a>Hinweise  
 Kovarianz ermöglicht Ihnen die Verwendung eines stärker abgeleiteten Typs als durch den generischen Parameter angegeben. Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.  
  
 Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="rules"></a>Regeln  
 Sie können das `Out`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.  
  
 In einer generischen Schnittstelle kann ein Typparameter als kovariant deklariert werden, wenn er die folgenden Bedingungen erfüllt:  
  
-   Der Typparameter wird nur als Rückgabetyp von Schnittstellenmethoden, und nicht als Typ von Methodenargumenten verwendet.  
  
    > [!NOTE]
    >  Es gibt allerdings eine Ausnahme zu dieser Regel. Wenn Sie in einer kovarianten Schnittstelle einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für diesen Delegaten verwenden. Weitere Informationen über kovariante und kontravariante generische Delegate finden Sie unter [Varianz in Delegaten](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
-   Der Typparameter wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.  
  
 In einem generischen Delegaten kann ein Typparameter kovariant deklariert werden, wenn sie nur als Methodenrückgabetyp verwendet und nicht für Methodenargumente verwendet wird.  
  
 Kovarianz und Kontravarianz werden für Verweistypen unterstützt, aber nicht für Werttypen.  
  
 In Visual Basic können Sie Ereignisse in Schnittstellen mit kovarianten deklarieren, ohne Typ des Delegaten angeben. Darüber hinaus werden kovariante Schnittstellen keine geschachtelten Klassen, Enumerationen und Strukturen, aber geschachtelte Schnittstellen.  
  
## <a name="behavior"></a>Verhalten  
 Die Methoden einer Schnittstelle, die einen kovarianten Typparameter hat, können mehr abgeleitete Typen als durch den Typparameter angegeben zurückgeben. Da z.B. in .NET Framework 4 Typ T in <xref:System.Collections.Generic.IEnumerable%601> kovariant ist, können Sie ein Objekt des `IEnumerabe(Of String)`-Typs an ein Objekt des `IEnumerable(Of Object)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden.  
  
 Ein kovarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem stärker abgeleiteten generischen Typparameter.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine kovariante generische Schnittstelle deklarieren, erweitern und implementieren. Es wird auch gezeigt, wie eine implizite Konvertierung für Klassen verwendet wird, die eine kovariante Schnittstelle implementieren.  
  
 [!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren, instanziieren und aufrufen. Es wird auch gezeigt, wie Sie die implizite Konvertierung für Delegattypen verwenden können.  
  
 [!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch
- [Varianz in generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
