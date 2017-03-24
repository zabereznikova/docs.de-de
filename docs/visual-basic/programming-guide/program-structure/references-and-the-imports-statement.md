---
title: Verweise und die Imports-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 283a27e7703b31a9aeed8f7e4104e89b7ff78525
ms.lasthandoff: 03/13/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a>Verweise und die Imports-Anweisung (Visual Basic)
Sie können externe Objekte zur Verfügung stellen zu Ihrem Projekt durch Auswahl der **Verweis hinzufügen** Befehl die **Projekt** Menü. Verweise in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können auf Assemblys zeigen, die vergleichbar Typbibliotheken jedoch mehr Informationen enthalten sind.  
  
## <a name="the-imports-statement"></a>Die Imports-Anweisung  
 Assemblys umfassen einen oder mehrere Namespaces. Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch hinzufügen eine `Imports` Anweisung, um ein Modul, das die Sichtbarkeit der Switch-Namespaces innerhalb des Moduls steuert. Die `Imports` -Anweisung stellt einen Kontextbereich, die nur den Teil eines eindeutigen Verweises zum Namespace verwenden kann.  
  
 Die `Imports` Anweisung hat die folgende Syntax:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`bezieht sich auf einen kurzen Namen, den Sie innerhalb des Codes verwenden können, um auf einen importierten Namespace zu verweisen. `Namespace`ist ein Namespace, die verfügbar sind, entweder durch einen Projektverweis, durch eine Definition innerhalb des Projekts oder durch eine vorherige `Imports` Anweisung.  
  
 Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Müssen sie nach jedem erscheinen `Option` -Anweisungen, falls vorhanden, aber vor allem anderen Code.  
  
> [!NOTE]
>  Verwechseln Sie nicht die Projektverweise mit den `Imports` Anweisung oder der `Declare` Anweisung. Projektverweisen werden externe Objekte, z. B. Objekte in Assemblys, auf [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekte. Die `Imports` Anweisung wird verwendet, um den Zugriff auf Projektverweise zu vereinfachen, bietet jedoch keinen Zugriff auf diese Objekte. Die `Declare` -Anweisung verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Verwenden von Aliasen mit der Imports-Anweisung  
 Die `Imports` -Anweisung erleichtert Zugriff auf Methoden von Klassen durch den Wegfall um explizit die vollqualifizierten Namen von verweisen. Aliase können Sie nur einen Teil eines Namespace einen benutzerfreundlicheren Namen zuweisen. Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text, der in mehreren Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars>-Modul in die <xref:Microsoft.VisualBasic?displayProperty=fullName>Namespace.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars> Um diese Konstante in einem Programm ohne Alias verwenden, müssen Sie den folgenden Code eingeben:  
  
 [!code-vb[VbVbalrApplication&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`Anweisungen muss immer die ersten Zeilen direkt nach einem `Option` Anweisungen in einem Modul. Das folgende Codefragment zeigt, wie zum Importieren und Zuweisen eines Alias für die <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>Modul:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>  
  
 [!code-vb[VbVbalrApplication&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Zukünftige Verweise auf diesen Namespace können wesentlich kürzer sein:  
  
 [!code-vb[VbVbalrApplication&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Wenn eine `Imports` -Anweisung keinen Aliasnamen, den importierten Namespace definierte Elemente ohne Qualifikation im Modul verwendet werden können. Wenn der Aliasname angegeben ist, muss er für Namen in diesem Namespace enthaltenen als Qualifizierer verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic>   
 [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
