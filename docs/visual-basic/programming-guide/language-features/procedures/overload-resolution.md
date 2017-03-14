---
title: "Overload Resolution (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "overload resolution"
  - "procedures, overloading"
  - "procedures, calling"
  - "procedure overloading, overload resolution"
  - "signatures, procedure"
  - "overloads, resolution"
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Overload Resolution (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler auf den Aufruf einer Prozedur trifft, die in mehreren überladenen Versionen definiert ist, muss er entscheiden, welche der Überladungen aufgerufen wird.  Dazu werden die folgenden Schritte ausgeführt:  
  
1.  **Zugriff.** Der Compiler schließt jede Überladung mit einer Zugriffsebene aus, die den Aufrufcode daran hindert, sie aufzurufen.  
  
2.  **Anzahl der Parameter.** Der Compiler entfernt alle Überladungen, die eine vom Aufruf abweichende Anzahl an Parametern definieren.  
  
3.  **Datentypen von Parametern.** Der Compiler zieht Instanzmethoden gegenüber Erweiterungsmethoden vor.  Wenn eine beliebige Instanzmethode gefunden wurde, die lediglich eine Erweiterungskonvertierung benötigt, um dem Prozeduraufruf zu entsprechen, werden alle Erweiterungsmethoden verworfen. Der Compiler verarbeitet dann ausschließlich geeignete Instanzmethoden.  Wenn keine solche Instanzmethode gefunden wird, setzt der Compiler die Verarbeitung sowohl mit Instanzmethoden als auch mit Erweiterungsmethoden fort.  
  
     In diesem Schritt entfernt der Compiler alle Überladungen, bei denen die Datentypen der aufrufenden Argumente nicht in die Parametertypen umgewandelt werden können, die in der Überladung definiert sind.  
  
4.  **Eingrenzende Konvertierungen.** Der Compiler entfernt alle Überladungen, die eine Eingrenzungskonvertierung aus dem Typ des aufrufenden Arguments in die definierten Parametertypen erfordern.  Dies gilt unabhängig davon, ob die Typüberprüfung \([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) den Wert `On` oder `Off` hat.  
  
5.  **Geringste Erweiterung.** Der Compiler betrachtet die übrigen Überladungen paarweise.  Bei jedem Paar werden die Datentypen der definierten Parameter verglichen.  Wenn alle Typen in einer Überladung zu den entsprechenden Typen in der anderen Überladung erweitert werden, entfernt der Compiler die letztere.  Das bedeutet, dass die Überladung mit dem geringsten Erweiterungsaufwand beibehalten wird.  
  
6.  **Einzelne Betrachtung.** Die Überladungen werden paarweise berücksichtigt, bis eine einzelne Überladung übrig bleibt, dann wird der Aufruf dieser Überladung aufgelöst.  Wenn der Compiler die Überladungen nicht bis auf eine einzelne reduzieren kann, generiert er einen Fehler.  
  
 Im folgenden Beispiel wird der Prozess veranschaulicht, mit dem bestimmt wird, welche überladenen Versionen aufgerufen werden sollen.  
  
 ![Flussdiagramm des Überladungsauflösungsprozesses](../../../../visual-basic/programming-guide/language-features/procedures/media/overloadres.gif "OverloadRes")  
Auflösung bei überladenen Versionen  
  
 Im folgenden Beispiel wird dieser Prozess der Überladungsauflösung dargestellt.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 Im ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments \(`Short`\) auf den Typ des entsprechenden Parameters \(`Byte`\) eingeschränkt wird.  Anschließend wird die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung \(`Short` und `Single`\) in den entsprechenden Typ der dritten Überladung \(`Integer` und `Single`\) erweitert wird.  Da die zweite Überladung eine geringere Erweiterung erfordert, wird sie vom Compiler für den Aufruf verwendet.  
  
 Im zweiten Aufruf kann der Compiler keine Überladung durch Einschränken ausschließen.  Die dritte Überladung wird aus dem gleichen Grund beseitigt wie im ersten Aufruf, da nämlich die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann.  Zwischen der ersten und zweiten Überladung kann der Compiler jedoch keine Auflösung ausführen.  Jede Überladung hat einen definierten Parametertyp, der in der anderen Überladung in den entsprechenden Typ erweitert wird \(`Byte` in `Short` und `Single` in `Double`\).  Aus diesem Grund generiert der Compiler einen Überladungsauflösungsfehler.  
  
## Überladene optionale und ParamArray\-Argumente  
 Wenn die Signaturen von zwei Überladungen einer Prozedur sich nur darin unterscheiden, dass der letzte Parameter in der einen Prozedur als [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) und in der anderen als [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) deklariert ist, löst der Compiler einen Aufruf dieser Prozedur folgendermaßen auf:  
  
|||  
|-|-|  
|Wenn der Aufruf das letzte Argument als Folgendes übergibt:|... löst der Compiler den Aufruf der Überladung auf, in der das letzte Argument als Folgendes deklariert ist:|  
|Kein Wert \(Argument ausgelassen\)|`Optional`|  
|Ein einzelner Wert|`Optional`|  
|Zwei oder mehr Werte in einer durch Trennzeichen getrennten Liste|`ParamArray`|  
|Ein Array beliebiger Länge \(einschließlich eines leeren Arrays\)|`ParamArray`|  
  
## Siehe auch  
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)