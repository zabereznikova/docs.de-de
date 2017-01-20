---
title: "Conditional Compilation in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conditional compilation, about conditional compilation"
  - "compilation, conditional"
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conditional Compilation in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Bei der *bedingten Kompilierung* werden besondere Codeblöcke in einem Programm selektiv kompiliert, während andere ignoriert werden.  
  
 Sie kann beispielsweise eingesetzt werden, wenn Sie Debuganweisungen schreiben möchten, die die Geschwindigkeit verschiedener Herangehensweisen an ein und dieselbe Programmieraufgabe vergleichen, oder eine Anwendung für mehrere Sprachen lokalisieren möchten.  Bedingte Kompilierungsanweisungen sind so konzipiert, dass sie nicht zur Laufzeit, sondern während der Kompilierung durchgeführt werden können.  
  
 Sie geben Codeblöcke an, die mit der `#If...Then...#Else`\-Direktive bedingt kompiliert werden sollen.  Um beispielsweise Versionen einer Anwendung aus demselben Quellcode in französischer und deutscher Sprache zu erstellen, müssen Sie plattformspezifische Codesegmente unter Verwendung der vordefinierten Konstanten `FrenchVersion` und `GermanVersion` in `#If...Then`\-Anweisungen einbetten.  Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 Wenn Sie den Wert der `FrenchVersion`\-Konstanten für bedingte Kompilierung während der Kompilierung auf `True` festlegen, wird der bedingte Code für die französische Version kompiliert.  Wenn Sie den Wert der `GermanVersion`\-Konstanten auf `True` festlegen, verwendet der Compiler die deutsche Version.  Wenn keine der Konstanten auf `True` festgelegt wurde, wird der Code aus dem letzten `Else`\-Block ausgeführt.  
  
> [!NOTE]
>  Die automatische Vervollständigung funktioniert beim Bearbeiten von Code und beim Verwenden von bedingten Kompilierungsdirektiven nicht, wenn der Code nicht Bestandteil der aktuellen Verzweigung ist.  
  
## Deklarieren von bedingten Kompilierungskonstanten  
 Für die Festlegung bedingter Kompilierungskonstanten gibt es drei Möglichkeiten:  
  
-   Im **Projekt\-Designer**  
  
-   Bei Verwendung des Befehlszeilencompilers in der Befehlszeile  
  
-   Im Code  
  
 Bedingte Kompilierungskonstanten verfügen über einen bestimmten Gültigkeitsbereich und können nicht vom Standardcode aus aufgerufen werden.  Der Gültigkeitsbereich einer bedingten Kompilierungskonstante ist davon abhängig, wie sie eingerichtet wurde.  In der folgenden Tabelle werden die Gültigkeitsbereiche von Konstanten aufgelistet, die jeweils mit einer der oben genannten Möglichkeiten deklariert wurden.  
  
|||  
|-|-|  
|Festlegung der Konstante|Gültigkeitsbereich der Konstante|  
|**Projekt\-Designer**|Öffentlich für alle Dateien des Projekts|  
|Befehlszeile|Öffentlich für alle Dateien, die an den Befehlszeilencompiler übergeben wurden|  
|`#Const`\-Anweisung im Code|Privat für die Datei, in der sie deklariert wurde|  
  
||  
|-|  
|So legen Sie Konstanten im Projekt\-Designer fest|  
|-   Bevor Sie die ausführbare Datei erstellen, müssen Sie im **Projekt\-Designer** Konstanten festlegen. Folgen Sie hierfür den unter [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) angegebenen Schritten.|  
  
||  
|-|  
|So legen Sie in der Befehlszeile Konstanten fest|  
|-   Verwenden Sie den **\/d**\-Schalter, um bedingte Kompilierungskonstanten einzugeben \(siehe folgendes Beispiel\):<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Zwischen dem **\/d**\-Schalter und der ersten Konstanten muss kein Leerzeichen stehen.  Weitere Informationen finden Sie unter [\/define](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Befehlszeilendeklarationen überschreiben die im **Projekt\-Designer** eingegebenen Deklarationen, löschen diese jedoch nicht.  Die im **Projekt\-Designer** festgelegten Argumente bleiben für spätere Kompilierungen wirksam.<br />     Wenn Konstanten in den Code selbst geschrieben werden, gibt es keine strengen Regeln bezüglich ihrer Platzierung, da ihr Gültigkeitsbereich das gesamte Modul umfasst, in dem sie deklariert wurden.|  
  
||  
|-|  
|So legen Sie Konstanten im Code fest|  
|-   Fügen Sie die Konstanten in den Deklarationsblock des Moduls ein, in dem sie verwendet werden.  Dadurch bleibt der Code geordnet und ist leichter zu lesen.|  
  
## Verwandte Themen  
  
|||  
|-|-|  
|Titel|Beschreibung|  
|[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Gibt Möglichkeiten dafür vor, wie Sie den Code so gestalten können, dass er einfacher zu lesen und zu verwalten ist.|  
  
## Verweis  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)