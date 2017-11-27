---
title: Bedingte Kompilierung in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 559380dc9baceb2fba4dca782e83f335f1bcd92d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="conditional-compilation-in-visual-basic"></a>Bedingte Kompilierung in Visual Basic
In *bedingte Kompilierung*, selektiv bestimmter Codeblöcke in einem Programm kompiliert werden, während andere ignoriert werden.  
  
 Sie möchten z. B. Schreiben Debuggen von Anweisungen, die die Geschwindigkeit des unterschiedliche Ansätze zur gleichen Programmiertask, oder Sie vergleichen kann eine Anwendung für mehrere Sprachen lokalisieren möchten. Anweisungen für die bedingte Kompilierung dienen während der Zeitpunkt der Kompilierung nicht zur Laufzeit ausgeführt.  
  
 Sie kennzeichnen die Codeblöcke mit bedingt kompiliert werden die `#If...Then...#Else` Richtlinie. Z. B. Französisch und Deutsch-Sprache erstellen Versionen der gleichen Anwendung aus dem Quellcode, die Sie plattformspezifischen Codesegmente im einbetten `#If...Then` Anweisungen, die mithilfe der definierten Konstanten `FrenchVersion` und `GermanVersion`. Im folgende Beispiel wird veranschaulicht, wie:  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 Wenn Sie den Wert der Festlegen der `FrenchVersion` Konstante für bedingte Kompilierung zu `True` zum Zeitpunkt der Kompilierung wird der bedingte Code für die französische Version kompiliert. Wenn Sie den Wert der Festlegen der `GermanVersion` zu Konstante `True`, verwendet der Compiler die deutsche Version. Wenn keine, um festgelegt ist `True`, den Code in den letzten `Else` -Block ausgeführt.  
  
> [!NOTE]
>  Automatische Vervollständigung wird not-Funktion beim Bearbeiten von code und bedingten Kompilierungsdirektiven verwenden, wenn der Code nicht Teil des aktuellen Branch ist.  
  
## <a name="declaring-conditional-compilation-constants"></a>Deklarieren von Konstanten für die bedingte Kompilierung  
 Sie können die Konstanten für die bedingte Kompilierung in eine von drei Arten festlegen:  
  
-   In der **Projekt-Designer**  
  
-   In der Befehlszeile, die bei Verwendung des Befehlszeilencompilers  
  
-   Im code  
  
 Bedingte Kompilierungskonstanten haben einen bestimmten Gültigkeitsbereich und können nicht aus der Standardcode zugegriffen werden. Der Bereich, der eine Konstante für bedingte Kompilierung ist abhängig von die Möglichkeit, die sie festgelegt ist. Die folgende Tabelle enthält den Bereich der Konstanten, die mit jeder der drei oben genannten Methoden deklariert werden.  
  
|Wie Konstante festgelegt wird|Umfang der Konstante|  
|---|---|  
|**Projekt-Designer**|Öffentlich für alle Dateien im Projekt|  
|Über die Befehlszeile|Öffentlich für alle Dateien, die für den Befehlszeilencompiler übergeben|  
|`#Const`die Anweisung im code|Für die Datei, in der sie deklariert ist, privat|  
  
|So legen Sie Konstanten in den Projekt-Designer fest|  
|---|  
|-Bevor die ausführbare Datei erstellen, legen Sie Konstanten in der **Projekt-Designer** gemäß den Schritten [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Konstanten in der Befehlszeile festlegen|  
|---|  
|– Verwenden Sie die **/d** Switch Konstanten für die bedingte Kompilierung wie im folgenden Beispiel eingeben:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Kein Speicherplatz ist erforderlich, zwischen den **/d** Switch und das erste Konstante. Weitere Informationen finden Sie unter [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Befehlszeile-Deklarationen überschreiben eingegebenen Deklarationen der **Projekt-Designer**, aber nicht gelöscht werden können. Legen Sie die Argumente **Projekt-Designer** bleiben für nachfolgende Kompilierungen wirksam.<br />     Wenn Konstanten im Code selbst schreiben, sind es keine strenge Regeln hinsichtlich ihrer Platzierung seit deren Bereich das gesamte Modul ist in dem sie deklariert werden.|  
  
|Um Konstanten im Code festgelegt werden.|  
|---|  
|-Fügen Sie die Konstanten in der Deklarationsblock des Moduls, in dem sie verwendet werden. Dadurch wird Ihr Code organisiert und leichter lesbar bleibt.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|---|---|  
|[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Enthält Vorschläge für erleichtert die Ihren Code lesen und zu verwalten.|  
  
## <a name="reference"></a>Verweis  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
