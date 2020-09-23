---
title: 'Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 0be49e7d4aacbb30956bda7f6ee8494a7ded8b78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071624"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)

Die Prozedur Deklaration bestimmt den Übergabe Mechanismus. Wenn ein Parameter als [ByRef](../../../language-reference/modifiers/byref.md)deklariert wird, erwartet Visual Basic, dass das entsprechende Argument als Verweis übergeben wird. Dies ermöglicht es der Prozedur, den Wert des Programmier Elements zu ändern, das dem Argument im aufrufenden Code zugrunde liegt. Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie den `ByRef` Übergabe Mechanismus im Prozedur aufzurufen überschreiben, indem Sie den Argument Namen in Klammern einschließen. Diese Klammern sind zusätzlich zu den Klammern angegeben, die die Argumentliste im-Befehl einschließen.  
  
 Der Aufruf Code kann einen [ByVal](../../../language-reference/modifiers/byval.md) -Mechanismus nicht überschreiben.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>So erzwingen Sie, dass ein Argument als Wert übermittelt wird  
  
- Wenn der entsprechende Parameter `ByVal` in der Prozedur deklariert ist, müssen Sie keine weiteren Schritte ausführen. Visual Basic erwartet bereits, dass das Argument als Wert übergeben wird.  
  
- Wenn der entsprechende Parameter `ByRef` in der Prozedur deklariert wird, schließen Sie das Argument in Klammern in den Prozedur aufrufen ein.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine `ByRef` Parameter Deklaration überschrieben. Beachten Sie in dem von Erzwingung erzwingt `ByVal` die zwei Ebenen von Klammern.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Wenn `str` in zusätzliche Klammern in der Argumentliste eingeschlossen ist, `setNewString` kann die Prozedur den Wert im aufrufenden Code nicht ändern und `MsgBox` zeigt "kann nicht ersetzt werden, wenn ByVal übergeben wird" angezeigt wird. Wenn `str` nicht in zusätzliche Klammern eingeschlossen ist, kann Sie von der Prozedur geändert werden, und es wird `MsgBox` angezeigt, dass dies ein neuer Wert für das inString-Argument ist.  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  

 Wenn Sie eine Variable als Verweis übergeben, müssen Sie dieses Verfahren mit dem- `ByRef` Schlüsselwort angeben.  
  
 Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben. Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../language-reference/modifiers/byval.md) -oder [ByRef](../../../language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen. Dadurch wird Ihr Code leichter lesbar.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Wenn eine Prozedur einen [ByRef](../../../language-reference/modifiers/byref.md)-Parameter deklariert, hängt die korrekte Ausführung des Codes möglicherweise davon ab, ob das zugrunde liegende Element im aufrufenden Code geändert werden kann. Wenn der aufrufende Code diesen Aufruf Mechanismus überschreibt, indem das Argument in Klammern eingeschlossen wird, oder wenn er ein nicht änderbares Argument übergibt, kann die Prozedur das zugrunde liegende Element nicht ändern. Dies kann zu unerwarteten Ergebnissen im aufrufenden Code führen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Es besteht immer ein potenzielles Risiko, dass eine Prozedur den Wert ändern kann, der einem Argument im aufrufenden Code zugrunde liegt. Stellen Sie sicher, dass dieser Wert geändert wird, und dass Sie darauf vorbereitet sind, ihn vor der Verwendung auf Gültigkeit zu überprüfen.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Wert- und Verweistypen](../data-types/value-types-and-reference-types.md)
