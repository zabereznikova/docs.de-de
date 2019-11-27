---
title: Call-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350163"
---
# <a name="call-statement-visual-basic"></a>Call-Anweisung (Visual Basic)

Überträgt die Steuerung an eine `Function`-, `Sub`-oder DLL-Prozedur (Dynamic-Link Library).  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>-Komponenten  

|||
|---|---|
|`procedureName`|Erforderlich Der Name der aufzurufenden Prozedur.|
|`argumentList`|Optional. Liste der Variablen oder Ausdrücke, die Argumente darstellen, die beim Aufrufen an die Prozedur übermittelt werden. Mehrere Argumente werden durch Kommas getrennt. Wenn Sie `argumentList`einschließen, müssen Sie es in Klammern einschließen.|
|||
  
## <a name="remarks"></a>Hinweise

 Sie können das `Call`-Schlüsselwort verwenden, wenn Sie eine Prozedur aufzurufen. Bei den meisten Prozedur aufrufen müssen Sie dieses Schlüsselwort nicht verwenden.

 Normalerweise verwenden Sie das `Call`-Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einem Bezeichner beginnt. Die Verwendung des `Call`-Schlüssel Worts für andere Verwendungszwecke wird nicht empfohlen.

 Wenn die Prozedur einen Wert zurückgibt, verwirft Sie die `Call`-Anweisung.

## <a name="example"></a>Beispiel

 Der folgende Code zeigt zwei Beispiele, in denen das `Call`-Schlüsselwort erforderlich ist, um eine Prozedur aufzurufen. In beiden Beispielen beginnt der aufgerufene Ausdruck nicht mit einem Bezeichner.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Declare-Anweisung](declare-statement.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
