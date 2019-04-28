---
title: Bedingte Kompilierung in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758456"
---
# <a name="conditional-compilation-in-visual-basic"></a>Bedingte Kompilierung in Visual Basic
In *für die bedingte Kompilierung*, selektiv bestimmte Codeblöcke in einem Programm kompiliert werden, während andere ignoriert werden.  
  
 Sie möchten z. B. Schreiben Debuggen-Anweisungen, die von der Geschwindigkeit der Ansätze mit den gleichen Programmiertask, oder Sie vergleichen kann eine Anwendung für mehrere Sprachen lokalisieren möchten. Anweisungen für die bedingte Kompilierung dienen, die während der Zeitpunkt der Kompilierung zur Laufzeit nicht ausgeführt.  
  
 Sie kennzeichnen Codeblöcke mit bedingt kompiliert werden die `#If...Then...#Else` Richtlinie. Z. B. Französisch und Deutsch-Sprache erstellen Versionen der gleichen Anwendung aus dem Quellcode, die Sie einbetten, plattformspezifischen Codesegmente in `#If...Then` Anweisungen, die mithilfe der definierten Konstanten `FrenchVersion` und `GermanVersion`. Im folgende Beispiel wird veranschaulicht, wie:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Wenn Sie festlegen, dass den Wert des der `FrenchVersion` Konstante für bedingte Kompilierung auf `True` zum Zeitpunkt der Kompilierung der bedingte Code für die französische Version kompiliert wird. Wenn Sie festlegen, dass den Wert des der `GermanVersion` zu Konstante `True`, verwendet der Compiler die deutsche Version. Wenn keine, um festgelegt ist `True`, den Code in den letzten `Else` -Block ausgeführt.  
  
> [!NOTE]
>  Automatische Vervollständigung wird nicht die Funktion beim Bearbeiten von code und mit bedingten Kompilierungsdirektiven, wenn der Code nicht Teil von current Branch ist.  
  
## <a name="declaring-conditional-compilation-constants"></a>Deklarieren von Konstanten für bedingte Kompilierung  
 Sie können die Konstanten für bedingte Kompilierung in eine von drei Arten festlegen:  
  
- In der **Projekt-Designer**  
  
- In der Befehlszeile, wenn Sie den Befehlszeilencompiler verwenden  
  
- In Ihrem code  
  
 Bedingte Kompilierungskonstanten haben einen speziellen Bereich und können nicht aus dem Standardcode zugegriffen werden. Der Bereich einer Konstante für bedingte Kompilierung ist abhängig von der sie eingerichtet wurde. Die folgende Tabelle enthält den Bereich der Konstanten, die mit jeder der drei oben genannten Methoden deklariert werden.  
  
|Festlegung der Konstante|Bereich der Konstante|  
|---|---|  
|**Projekt-Designer**|Öffentlich für alle Dateien im Projekt|  
|Befehlszeile|Öffentlich für alle Dateien, die an den Befehlszeilencompiler|  
|`#Const` -Anweisung in code|Privat für die Datei, die in der sie deklariert ist|  
  
|Zum Festlegen von Konstanten in den Projekt-Designer|  
|---|  
|– Bevor Sie die ausführbare Datei erstellen, legen Sie Konstanten der **Projekt-Designer** anhand der Schritte im [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Konstanten in der Befehlszeile festlegen.|  
|---|  
|– Verwenden Sie die **/d** Switch Konstanten für bedingte Kompilierung, wie im folgenden Beispiel eingeben:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Kein Speicherplatz ist erforderlich, zwischen den **/d** Switch und das erste Konstante. Weitere Informationen finden Sie unter [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Befehlszeile-Deklarationen Überschreiben von Deklarationen, die in eingegebenen der **Projekt-Designer**, aber nicht gelöscht werden können. Legen Sie die Argumente in **Projekt-Designer** bleiben für nachfolgende Kompilierungen wirksam.<br />     Beim Konstanten im Code selbst schreiben möchten, stehen keine strengen Regeln bezüglich ihrer Platzierung, da deren Bereich das gesamte Modul ist in dem sie deklariert werden.|  
  
|Um Konstanten im Code festgelegt werden.|  
|---|  
|-Fügen Sie die Konstanten in der Deklarationsblock des Moduls, in dem sie verwendet werden. Dadurch bleibt Ihr Code organisiert und leichter zu lesen.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|---|---|  
|[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Enthält Vorschläge für Ihren Code leicht zu lesen und zu verwalten.|  
  
## <a name="reference"></a>Referenz  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
