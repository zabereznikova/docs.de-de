---
title: Bedingte Kompilierung
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 19a2c70941a9a72574f7e624743def74b80c4e39
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347461"
---
# <a name="conditional-compilation-in-visual-basic"></a>Bedingte Kompilierung in Visual Basic
Bei der *bedingten Kompilierung*werden bestimmte Code Blöcke in einem Programm selektiv kompiliert, während andere ignoriert werden.  
  
 Beispielsweise können Sie Debuganweisungen schreiben, die die Geschwindigkeit verschiedener Ansätze mit derselben Programmieraufgabe vergleichen, oder Sie möchten eine Anwendung für mehrere Sprachen lokalisieren. Bedingte Kompilierungs Anweisungen sind so konzipiert, dass Sie zur Kompilierzeit und nicht zur Laufzeit ausgeführt werden.  
  
 Code Blöcke, die mit der `#If...Then...#Else`-Direktive bedingt kompiliert werden sollen. Wenn Sie z. b. Französisch-und deutschsprachige Versionen derselben Anwendung aus demselben Quellcode erstellen möchten, Betten Sie plattformspezifische Code Segmente in `#If...Then` Anweisungen ein, indem Sie die vordefinierten Konstanten `FrenchVersion` und `GermanVersion`. Im folgenden Beispiel wird veranschaulicht, wie:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Wenn Sie den Wert der `FrenchVersion` bedingte Kompilierungs Konstante zum Zeitpunkt der Kompilierung auf `True` festlegen, wird der bedingte Code für die französische Version kompiliert. Wenn Sie den Wert der `GermanVersion` Konstante auf `True`festlegen, verwendet der Compiler die deutsche Version. Wenn keines der beiden `True`festgelegt ist, wird der Code im letzten `Else`-Block ausgeführt.  
  
> [!NOTE]
> Die automatische Vervollständigung funktioniert nicht, wenn Code bearbeitet und bedingte Kompilierungs Direktiven verwendet werden, wenn der Code nicht Teil der aktuellen Verzweigung ist.  
  
## <a name="declaring-conditional-compilation-constants"></a>Deklarieren bedingter Kompilierungs Konstanten  
 Sie können auf eine von drei Arten bedingte Kompilierungs Konstanten festlegen:  
  
- Im **Projekt-Designer**  
  
- Bei Verwendung des Befehlszeilen Compilers an der Befehlszeile  
  
- In Ihrem Code  
  
 Die Konstanten für die bedingte Kompilierung haben einen speziellen Bereich und können nicht über Standard Code aufgerufen werden. Der Gültigkeitsbereich einer Konstanten für die bedingte Kompilierung hängt davon ab, wie er festgelegt wird. In der folgenden Tabelle wird der Gültigkeitsbereich der Konstanten aufgelistet, die mit den drei oben erwähnten Methoden deklariert werden.  
  
|Festlegen der Konstante|Gültigkeitsbereich der Konstante|  
|---|---|  
|**Projekt-Designer**|Öffentlich für alle Dateien im Projekt|  
|Befehlszeile|Öffentlich für alle Dateien, die an den Befehlszeilen Compiler übermittelt werden|  
|`#Const`-Anweisung im Code|Privat für die Datei, in der Sie deklariert ist|  
  
|So legen Sie Konstanten im Projekt-Designer fest|  
|---|  
|-Legen Sie vor dem Erstellen der ausführbaren Datei Konstanten im **Projekt-Designer** fest, indem Sie die Schritte unter Verwalten von [Projekt-und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)befolgen.|  
  
|So legen Sie Konstanten in der Befehlszeile fest|  
|---|  
|-Verwenden Sie den Schalter **-d** , um die Konstanten für die bedingte Kompilierung einzugeben, wie im folgenden Beispiel gezeigt:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Zwischen dem Schalter " **-d** " und der ersten Konstante ist kein Leerzeichen erforderlich. Weitere Informationen finden Sie unter [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Befehlszeilen Deklarationen überschreiben Deklarationen, die im **Projekt-Designer**eingegeben wurden, löschen Sie aber nicht. Die im **Projekt-Designer** festgelegten Argumente bleiben für nachfolgende Kompilierungen wirksam.<br />     Beim Schreiben von Konstanten im Code selbst gibt es keine strengen Regeln für die Platzierung, da der Gültigkeitsbereich das gesamte Modul ist, in dem Sie deklariert werden.|  
  
|So legen Sie Konstanten im Code fest|  
|---|  
|-Platzieren Sie die Konstanten im Deklarations Block des Moduls, in dem Sie verwendet werden. Dadurch wird der Code organisiert und leichter lesbar.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|---|---|  
|[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Bietet Vorschläge, wie Sie Ihren Code auf einfache Weise lesen und warten können.|  
  
## <a name="reference"></a>Verweis  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
