---
title: Call-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392758"
---
# <a name="call-statement-visual-basic"></a>Call-Anweisung (Visual Basic)

Überträgt die Steuerung an eine `Function`-, `Sub`-oder DLL-Prozedur (Dynamic-Link Library).

## <a name="syntax"></a>Syntax

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a>Teile

|||
|---|---|
|`procedureName`|Erforderlich. Der Name der aufzurufenden Prozedur.|
|`argumentList`|Optional. Liste der Variablen oder Ausdrücke, die Argumente darstellen, die beim Aufrufen an die Prozedur übermittelt werden. Mehrere Argumente werden durch Kommas getrennt. Wenn Sie `argumentList` einschließen, müssen Sie Sie in Klammern einschließen.|
|||
  
## <a name="remarks"></a>Hinweise

 Sie können das Schlüsselwort `Call` verwenden, wenn Sie eine Prozedur aufzurufen. Bei den meisten Prozedur aufrufen müssen Sie dieses Schlüsselwort nicht verwenden.

 Normalerweise verwenden Sie das Schlüsselwort "`Call`", wenn der aufgerufene Ausdruck nicht mit einem Bezeichner beginnt. Die Verwendung des Schlüssel Worts "`Call`" für andere Verwendungszwecke wird nicht empfohlen.

 Wenn die Prozedur einen Wert zurückgibt, wird Sie durch die `Call`-Anweisung verworfen.

## <a name="example"></a>Beispiel

 Der folgende Code zeigt zwei Beispiele, in denen das `Call`-Schlüsselwort erforderlich ist, um eine Prozedur aufzurufen. In beiden Beispielen beginnt der aufgerufene Ausdruck nicht mit einem Bezeichner.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Declare-Anweisung](declare-statement.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
