---
title: "Local Type Inference (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "local type inference"
  - "vb.TypeInfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Option Infer statement"
  - "local type inference [Visual Basic]"
  - "implicitly-typed local variables [Visual Basic]"
  - "variables [Visual Basic], type inference"
  - "inference [Visual Basic]"
  - "type inference [Visual Basic]"
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 43
---
# Local Type Inference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Der Visual Basic \-Compiler ermittelt durch *Typrückschluss* die Datentypen lokaler Variablen, die ohne eine `As`\-Klausel deklariert werden.  Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab.  Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt. Im Ergebnis der Deklarationen sind sowohl `num1` als auch `num2` stark typisiert als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_1.vb)]  
  
> [!NOTE]
>  Wenn Sie nicht möchten, dass `num2` im vorherigen Beispiel als `Integer` typisiert wird, können Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3` einen anderen Typ angeben.  
  
 Der lokale Typrückschluss ist auf der Prozedurebene gültig.  Damit können keine Variablen auf der Modulebene deklariert werden \(d. h. in einer Klasse, einer Struktur, einem Modul oder einer Schnittstelle, jedoch nicht in einer Prozedur oder in einem Block\).  Wenn im vorherigen Beispiel `num2` statt einer lokalen Variablen in einer Prozedur ein Feld einer Klasse gewesen wäre, würde die Deklaration bei aktivierter `Option Strict` \(On\) einen Fehler verursachen und `num2` bei deaktivierter `Option Strict` \(Off\) als `Object` klassifizieren.  Entsprechend gilt ein lokaler Typrückschluss nicht für Verfahrensebenenvariablen, die als `Static` deklariert sind.  
  
## Typrückschluss undspäte Bindung  
 Code, in dem Typrückschluss verwendet wird, ähnelt Code, der auf später Bindung beruht.  Beim Typrückschluss werden Variablen jedoch stark typisiert, statt sie als `Object` zu belassen.  Der Typ einer Variablen wird vom Compiler zur Kompilierungszeit anhand des Initialisierers der Variable ermittelt, um früh gebundenen Code zu erzeugen.  Im vorherigen Beispiel wird `num2` wie `num1` als `Integer` typisiert.  
  
 Das Verhalten früh gebundener Variablen unterscheidet sich von dem spät gebundener Variablen, deren Typ nur zur Laufzeit bekannt ist.  Durch ein frühes Erkennen des Typs kann der Compiler Probleme vor der Ausführung erkennen, Speicher genau belegen und weitere Optimierungen durchführen.  Außerdem ermöglicht die frühe Bindung der integrierten Entwicklungsumgebung \(IDE\) von Visual Basic, IntelliSense\-Hilfen für die Member eines Objekts bereitzustellen.  Frühe Bindung ist auch aus Leistungsgründen zu bevorzugen.  Der Grund hierfür besteht darin, dass alle in einer spät gebundenen Variable gespeicherten Daten als Typ `Object` umschlossen werden müssen und das Programm durch Zugriffe auf Member dieses Typs zur Laufzeit langsamer wird.  
  
## Beispiele  
 Ein Typrückschluss erfolgt beim Initialisieren einer lokalen Variablen, die ohne `As`\-Klausel deklariert wurde.  Der Compiler verwendet den Typ des zugewiesenen Anfangswerts als Typ der Variablen.  Beispielsweise wird in jeder der folgenden Codezeilen jeweils eine Variable vom Typ `String` deklariert.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_2.vb)]  
  
 Im folgenden Code werden zwei gleichwertige Möglichkeiten veranschaulicht, ein Array mit Ganzzahlen zu erstellen.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_3.vb)]  
  
 Mit Typrückschluss können Sie den Typ einer Schleifensteuerungsvariablen auf einfache Weise ermitteln.  Im folgenden Code wird vom Compiler mit Typrückschluss abgeleitet, dass `number` ein `Integer` ist, da `someNumbers2` aus dem vorherigen Beispiel ein Array mit Ganzzahlen ist.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_4.vb)]  
  
 Lokaler Typrückschluss kann in `Using`\-Anweisungen verwendet werden, um den Typ des Ressourcennamens festzulegen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_5.vb)]  
  
 Der Typ einer Variablen kann auch aus den Rückgabewerten von Funktionen abgeleitet werden, wie im folgenden Beispiel veranschaulicht.  Sowohl `pList1` als auch `pList2` ist ein Array von Prozessen, da `Process.GetProcesses` ein Array von Prozessen zurückgibt.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_6.vb)]  
  
## Option Infer  
 `Option Infer` können Sie angeben, ob lokaler Typrückschluss in einer bestimmten Datei zulässig ist.  Geben Sie am Anfang der Datei eine der folgenden Anweisungen ein, um die Option zu aktivieren oder zu sperren.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Wenn Sie in Ihrem Code keinen Wert für `Option Infer` angeben, ist die Standardeinstellung des Compilers `Option Infer On`.  Bei Projekten, die von [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb-orcas-long-md.md)] oder einer früheren Version aktualisiert wurden, ist die Compilerstandardeinstellung `Option Infer Off`.  
  
 Wenn der für `Option Infer` in einer Datei festgelegte Wert dem in der IDE oder auf der Befehlszeile festgelegten Wert widerspricht, hat der Wert in der Datei Vorrang.  
  
 Weitere Informationen finden Sie unter [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  
  
## Beschränkungen  
 Typrückschluss kann nur für nicht statische, lokale Variablen verwendet werden, und nicht, um den Typ von Klassenfeldern, Eigenschaften oder Funktionen zu ermitteln.  
  
## Siehe auch  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [\/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)