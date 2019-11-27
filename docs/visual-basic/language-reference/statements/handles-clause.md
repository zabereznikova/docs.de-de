---
title: Handles-Klausel
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 2fecad919722f3da25c48f133a9c92b5e683d5e4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345911"
---
# <a name="handles-clause-visual-basic"></a>Handles-Klausel (Visual Basic)
Deklariert, dass eine Prozedur ein angegebenes Ereignis behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>-Komponenten  
 `proceduredeclaration`  
 Die `Sub`-Prozedurdeklaration für die Prozedur, die das Ereignis verarbeitet.  
  
 `eventlist`  
 Listet die Ereignisse für `proceduredeclaration` für die Verarbeitung auf, durch Kommas getrennt. Die Ereignisse müssen durch die Basisklasse für die aktuelle Klasse oder durch ein mithilfe des Schlüsselworts `WithEvents` deklariertes Objekt ausgelöst werden.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `Handles` -Schlüsselwort am Ende der Prozedurdeklaration, damit sie Ereignisse verarbeitet, die durch eine mithilfe des Schlüsselworts `WithEvents` deklarierte Objektvariable ausgelöst wurden. Das Schlüsselwort `Handles` kann zudem in einer abgeleiteten Klasse verwendet werden, um Ereignisse aus einer Basisklasse zu verarbeiten.  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede. Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen. Weitere Informationen finden Sie unter [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Für benutzerdefinierte Ereignisse ruft die Anwendung die `AddHandler`-Zugriffsmethode des Ereignisses auf, wenn die Prozedur als ein Ereignishandler hinzugefügt wird. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 Im folgenden Beispiel wird gezeigt, wie eine abgeleitete Klasse die `Handles`-Anweisung zum Verarbeiten eines Ereignisses aus einer Basisklasse verwenden kann.  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält zwei Ereignishandler für die Schaltfläche für ein **WPF-Anwendungs** Projekt.  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel entspricht dem vorherigen Beispiel. Die `eventlist` in der `Handles`-Klausel enthält die Ereignisse für beide Tasten.  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a>Siehe auch

- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
