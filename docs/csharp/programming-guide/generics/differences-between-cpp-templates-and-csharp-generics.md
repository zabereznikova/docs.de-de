---
title: "Unterschiede zwischen C++-Vorlagen und C#-Generika (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Generika [C#], Im Vergleich zu C++-Vorlagen"
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Unterschiede zwischen C++-Vorlagen und C#-Generika (C#-Programmierhandbuch)
Bei C\#\-Generika und C\+\+\-Vorlagen handelt es sich um Sprachfeatures, die parametrisierte Typen unterstützen.  Es gibt jedoch viele Unterschiede zwischen diesen Sprachfeatures.  Auf der Syntaxebene sind C\#\-Generika ein einfacherer Ansatz für parametrisierte Typen, denn sie haben nicht die Komplexität von C\+\+\-Vorlagen.  Außerdem versucht C\# nicht, die gesamte Funktionalität zur Verfügung zu stellen, die C\+\+\-Vorlagen bereitstellen.  Auf der Implementierungsebene besteht der Hauptunterschied darin, dass die Ersetzung generischer C\#\-Typen zur Laufzeit erfolgt und die Informationen zum generischen Typ instanziierter Objekte erhalten bleiben.  Weitere Informationen finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 Zwischen C\#\-Generika und C\+\+\-Vorlagen bestehen im Wesentlichen folgende Unterschiede:  
  
-   C\#\-Generika bieten nicht dieselbe Flexibilität wie C\+\+\-Vorlagen.  So ist es zum Beispiel nicht möglich, in einer generischen C\#\-Klasse arithmetische Operatoren aufzurufen. Benutzerdefinierte Operatoren können jedoch aufgerufen werden.  
  
-   C\# lässt keine nicht typisierten Vorlagenparameter zu, z. B. `template C<int i> {}`.  
  
-   C\# unterstützt keine explizite Spezialisierung, d. h. die benutzerdefinierte Implementierung einer Vorlage für einen bestimmten Typ.  
  
-   C\# unterstützt keine partielle Spezialisierung, d. h. die benutzerdefinierte Implementierung für eine Teilmenge der Typargumente.  
  
-   C\# lässt nicht zu, dass der Typparameter als Basisklasse für den generischen Typ verwendet wird.  
  
-   C\# unterstützt keine Standardtypen für Typparameter.  
  
-   In C\# kann ein generischer Typparameter nicht selbst generisch sein, obwohl konstruierte Typen als Generika verwendet werden können.  C\+\+ lässt Vorlagenparameter zu.  
  
-   C\+\+ lässt Code zu, der möglicherweise nicht für alle Typparameter einer Vorlage gültig ist. Die Gültigkeit wird für den spezifischen Typ überprüft, der als Typparameter verwendet wird.  In C\# muss der Code in einer Klasse so geschrieben werden, dass er für alle Typen gültig ist, die die Einschränkungen erfüllen.  So ist es zum Beispiel in C\+\+ möglich, eine Funktion zu schreiben, die die arithmetischen Operatoren `+` und `-` auf Objekte des Typparameters anwendet. Dies führt bei der Instanziierung der Vorlage zu einem Fehler, wenn der bei der Instanziierung verwendete Typ diese Operatoren nicht unterstützt.  C\# lässt dies nicht zu. Es werden lediglich solche Sprachkonstrukte zugelassen, die aus den Einschränkungen abgeleitet werden können.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Vorlagen](/visual-cpp/cpp/templates-cpp)