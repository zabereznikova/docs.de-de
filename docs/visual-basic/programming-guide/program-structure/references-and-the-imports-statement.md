---
title: Verweise und die Imports-Anweisung (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60c62eae57ae127fcbb860fe72853604802cccd9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Verweise und die Imports-Anweisung (Visual Basic)
Sie können externe Objekte verfügbar machen zu Ihrem Projekt durch Auswahl der **Verweis hinzufügen** Befehl der **Projekt** im Menü. Verweise in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können zeigen auf Assemblys, die wie Typbibliotheken jedoch mehr Informationen enthalten sind.  
  
## <a name="the-imports-statement"></a>Imports-Anweisung  
 Assemblys umfassen einen oder mehrere Namespaces. Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch Hinzufügen einer `Imports` Anweisung, um ein Modul, das die Sichtbarkeit von dieser Assembly Namespaces innerhalb des Moduls gesteuert. Die `Imports` Anweisung stellt einen Kontextbereich, die nur den Teil des Namespaces erforderlich, geben Sie einen eindeutigen Verweis verwenden kann.  
  
 Die `Imports` Anweisung hat folgende Syntax:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`bezieht sich auf einen kurzen Namen, den Sie innerhalb des Codes verwenden können, um auf einen importierten Namespace zu verweisen. `Namespace`ist ein Namespace ist verfügbar, entweder durch einen Projektverweis, durch eine Definition innerhalb des Projekts oder durch einen vorherigen `Imports` Anweisung.  
  
 Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Müssen sie nach allen stehen `Option` Anweisungen, falls vorhanden, jedoch vor jedem anderen Code.  
  
> [!NOTE]
>  Verwechseln Sie nicht die Projektverweise mit der `Imports` Anweisung oder der `Declare` Anweisung. Projektverweise auf externe Objekte, z. B. Objekte in Assemblys, verfügbar machen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Projekte. Die `Imports` -Anweisung wird verwendet, um den Zugriff auf Projektverweise vereinfachen, jedoch keinen Zugriff auf diese Objekte. Die `Declare` Anweisung wird verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Verwenden von Aliasen mit der Imports-Anweisung  
 Die `Imports` Anweisung erleichtert es Zugriff auf Methoden von Klassen durch den Wegfall um explizit die vollqualifizierten Namen von verweisen. Aliase können Sie nur einen Teil eines Namespace einen benutzerfreundlicheren Namen zuweisen. Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text, der in mehreren Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars> Modul in die <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace. Um diese Konstante in einem Programm ohne Alias zu verwenden, müssten Sie den folgenden Code eingeben:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`Anweisungen muss immer die ersten Zeilen, die unmittelbar nach einem `Option` Anweisungen in einem Modul. Das folgende Codefragment zeigt, wie zum Importieren und einen Alias Zuweisen der <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> Modul:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Zukünftige Verweise auf diesen Namespace können deutlich kürzer sein:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Wenn ein `Imports` -Anweisung keines Aliasnamens, in den importierten Namespace definierte Elementen können im Modul ohne Qualifizierung verwendet werden. Wenn der Aliasname angegeben wird, muss sie für Namen, die in diesem Namespace enthaltenen als Qualifizierer verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
