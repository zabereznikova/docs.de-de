---
title: Verweise und die Imports-Anweisung
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347279"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Verweise und die Imports-Anweisung (Visual Basic)
Sie können externe Objekte für Ihr Projekt verfügbar machen, indem Sie im Menü **Projekt** den Befehl **Verweis hinzufügen** auswählen. Verweise in Visual Basic können auf Assemblys verweisen, die wie Typbibliotheken vorliegen, aber weitere Informationen enthalten.  
  
## <a name="the-imports-statement"></a>Die Imports-Anweisung  
 Assemblys enthalten einen oder mehrere Namespaces. Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie einem Modul, das die Sichtbarkeit der Namespaces dieser Assembly innerhalb des Moduls steuert, auch eine `Imports`-Anweisung hinzufügen. Die `Imports`-Anweisung stellt einen Bereichs Kontext bereit, in dem Sie nur den Teil des-Namespace verwenden können, der zum Bereitstellen eines eindeutigen Verweises erforderlich ist.  
  
 Die `Imports`-Anweisung weist die folgende Syntax auf:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` verweist auf einen Kurznamen, den Sie im Code verwenden können, um auf einen importierten Namespace zu verweisen. `Namespace` ist ein Namespace, der entweder über einen Projekt Verweis, über eine Definition innerhalb des Projekts oder eine vorherige `Imports` Anweisung verfügbar ist.  
  
 Ein Modul kann eine beliebige Anzahl von `Imports`-Anweisungen enthalten. Sie müssen nach allen `Option`-Anweisungen (sofern vorhanden), aber vor einem anderen Code angezeigt werden.  
  
> [!NOTE]
> Verwechseln Sie Projekt Verweise nicht mit der `Imports`-Anweisung oder der `Declare`-Anweisung. Projekt Verweise machen externe Objekte (z. b. Objekte in Assemblys) für Visual Basic Projekte verfügbar. Die `Imports`-Anweisung wird verwendet, um den Zugriff auf Projekt Verweise zu vereinfachen, bietet aber keinen Zugriff auf diese Objekte. Die `Declare`-Anweisung wird verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (dll) zu deklarieren.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Verwenden von Aliasen mit der Imports-Anweisung  
 Die `Imports`-Anweisung vereinfacht den Zugriff auf Methoden von Klassen, da die Notwendigkeit entfällt, die voll qualifizierten Namen von verweisen explizit einzugeben. Mit Aliasen können Sie nur einem Teil eines Namespace einen freundlicheren Namen zuweisen. Beispielsweise ist die Reihenfolge der Wagen Rücklauf/Zeilenvorschub, die bewirkt, dass ein einzelnes Textzeile in mehreren Zeilen angezeigt wird, Teil des <xref:Microsoft.VisualBasic.ControlChars> Moduls im <xref:Microsoft.VisualBasic?displayProperty=nameWithType>-Namespace. Wenn Sie diese Konstante in einem Programm ohne Alias verwenden möchten, müssen Sie den folgenden Code eingeben:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports`-Anweisungen müssen immer die ersten Zeilen sein, die direkt nach allen `Option` Anweisungen in einem Modul stehen. Das folgende Code Fragment zeigt, wie Sie einen Alias importieren und dem <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>-Modul zuweisen:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Zukünftige Verweise auf diesen Namespace können erheblich kürzer sein:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Wenn eine `Imports` Anweisung keinen Aliasnamen enthält, können innerhalb des importierten Namespace definierte Elemente im Modul ohne Qualifizierung verwendet werden. Wenn der Aliasname angegeben ist, muss er als Qualifizierer für Namen verwendet werden, die in diesem Namespace enthalten sind.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Namespaces in Visual Basic](namespaces.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
