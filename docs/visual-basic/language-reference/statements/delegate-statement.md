---
title: Delegate-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 8dec28620b0409f05007b2c0b1c1fd4494c2d7c8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404757"
---
# <a name="delegate-statement"></a>Delegate-Anweisung
Wird zum Deklarieren eines Delegaten verwendet. Ein Delegat ist ein Verweistyp, der auf eine `Shared` Methode eines Typs oder auf eine Instanzmethode eines Objekts verweist. Eine beliebige Prozedur mit übereinstimmenden Parametern und Rückgabe Typen kann verwendet werden, um eine Instanz dieser Delegatklasse zu erstellen. Die Prozedur kann später mithilfe der Delegatinstanz aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`attrlist`|Dies ist optional. Liste der Attribute, die für diesen Delegaten gelten. Mehrere Attribute werden durch Kommas getrennt. Sie müssen die [Attribut Liste](attribute-list.md) in spitzen Klammern (" `<` " und " `>` ") einschließen.|  
|`accessmodifier`|Optional. Gibt an, welcher Code auf den Delegaten zugreifen kann. Kann eines der folgenden Elemente sein:<br /><br /> - [Öffentlich](../modifiers/public.md). Sämtlicher Code, der auf das Element zugreifen kann, das den Delegaten deklariert, kann darauf zugreifen.<br />-   [Geschützt](../modifiers/protected.md). Nur Code in der Klasse des Delegaten oder einer abgeleiteten Klasse kann darauf zugreifen.<br />-   [Friend](../modifiers/friend.md). Nur Code in derselben Assembly kann auf den Delegaten zugreifen.<br />- [Privat](../modifiers/private.md). Nur Code innerhalb des Elements, das den Delegaten deklariert, kann darauf zugreifen.<br /><br /> - [Geschützter Freund](../modifiers/protected-friend.md) Nur der Code innerhalb der Klasse des Delegaten, einer abgeleiteten Klasse oder derselben Assembly kann auf den Delegaten zugreifen. <br />- [Privat geschützt](../modifiers/private-protected.md) Nur Code in der Klasse des Delegaten oder in einer abgeleiteten Klasse in derselben Assembly kann auf den Delegaten zugreifen. |  
|`Shadows`|Optional. Gibt an, dass dieser Delegat ein identisch benanntes Programmier Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt. Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.<br /><br /> Ein schattiertes Element steht in der abgeleiteten Klasse, die es spiegelt, nicht zur Verfügung, und zwar mit Ausnahme von dem Punkt, wo nicht auf das Shadowing-Element zugriffen werden kann. Wenn ein-Element z. b `Private` . einen Schatten für ein Basisklassen Element besitzt, greift Code, der nicht über die Berechtigung für den Zugriff auf das Element verfügt, `Private` stattdessen auf das Basisklassen Element|  
|`Sub`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Deklariert dieses Verfahren als eine `Sub` Delegatprozedur, die keinen Wert zurückgibt.|  
|`Function`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Deklariert diese Prozedur als eine `Function` Delegatprozedur, die einen Wert zurückgibt.|  
|`name`|Erforderlich. Der Name des Delegattyps. befolgt Standard-Namenskonventionen für Variablen.|  
|`typeparamlist`|Optional. Liste der Typparameter für diesen Delegaten. Mehrere Typparameter werden durch Kommas getrennt. Optional kann jeder Typparameter mithilfe von `In` und `Out` generischen modifizierervariablen als Variant deklariert werden. Sie müssen die [Typliste](type-list.md) in Klammern einschließen und mit dem `Of` Schlüsselwort bereitstellen.|  
|`parameterlist`|Optional. Liste von Parametern, die beim Aufrufen an die Prozedur übermittelt werden. Sie müssen die [Parameter Liste](parameter-list.md) in Klammern einschließen.|  
|`type`|Erforderlich, wenn Sie eine `Function` Prozedur angeben. Datentyp des Rückgabewerts.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `Delegate` -Anweisung definiert die Parameter-und Rückgabe Typen einer Delegatklasse. Eine beliebige Prozedur mit übereinstimmenden Parametern und Rückgabe Typen kann verwendet werden, um eine Instanz dieser Delegatklasse zu erstellen. Die Prozedur kann später mithilfe der Delegatinstanz aufgerufen werden, indem die-Methode des Delegaten aufgerufen wird `Invoke` .  
  
 Delegaten können auf Namespace-, Modul-, Klassen-oder Struktur Ebene deklariert werden, jedoch nicht innerhalb einer Prozedur.  
  
 Jede Delegatklasse definiert einen Konstruktor, dem die Spezifikation einer Objektmethode übergeben wird. Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda-Ausdruck sein.  
  
 Verwenden Sie die folgende Syntax, um einen Verweis auf eine Methode festzulegen:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Der Typ von `expression` muss zur Kompilierungszeit der Name einer Klasse oder Schnittstelle sein, die eine Methode des angegebenen Namens enthält, deren Signatur mit der Signatur der Delegatklasse übereinstimmt. Bei `methodname` kann es sich um eine freigegebene Methode oder um eine Instanzmethode handeln. Der `methodname` ist nicht optional, selbst dann nicht, wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Verwenden Sie die folgende Syntax, um einen Lambda-Ausdruck festzulegen:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 Die Signatur der Funktion muss mit der des Delegattyps übereinstimmen. Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Weitere Informationen über Delegaten finden Sie unter [Delegaten](../../programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Delegate` -Anweisung verwendet, um einen Delegaten für die Verwendung zweier Zahlen und die Rückgabe einer Zahl zu deklarieren. Die `DelegateTest` -Methode nimmt eine Instanz eines Delegaten dieses Typs an und verwendet diese, um Paare von Zahlen zu verarbeiten.  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [AddressOf-Operator](../operators/addressof-operator.md)
- [Natürlich](of-clause.md)
- [Delegaten](../../programming-guide/language-features/delegates/index.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)
- [Geben Sie in](../modifiers/in-generic-modifier.md)
- [Vorgenommen](../modifiers/out-generic-modifier.md)
