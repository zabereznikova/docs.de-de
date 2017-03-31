---
title: Unterschiede zwischen C++-Vorlagen und C#-Generika (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d3171b1e3f48907778be6e256780e06bad36481f
ms.lasthandoff: 03/13/2017

---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a>Unterschiede zwischen C++-Vorlagen und C#-Generika (C#-Programmierhandbuch)
C#-Generika und C++-Vorlagen sind Sprachfunktionen, die Unterstützung für parametrisierte Typen ermöglichen. Es gibt jedoch viele Unterschiede zwischen den beiden. Auf der Syntaxebene sind C#-Generika ein einfacherer Ansatz für parametrisierte Typen ohne die Komplexität von C++-Vorlagen. Darüber hinaus versucht C# nicht alle Funktionen bereitzustellen, die C++-Vorlagen bereitstellen. Auf der Ebene der Implementierung ist der wichtigste Unterschied, dass C#-Ersetzungen des generischen Typs zur Laufzeit durchgeführt werden und allgemeine Informationen für die instanziierten Objekte beibehalten werden. Weitere Informationen finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 Die folgenden sind die Hauptunterschiede zwischen C#-Generika und C++-Vorlagen:  
  
-   C#-Generika bieten nicht die gleiche Menge an Flexibilität wie C++-Vorlagen. Es ist z.B. nicht möglich, arithmetische Operatoren in einer generischen Klasse von C# aufzurufen, obwohl es möglich ist, benutzerdefinierte Operatoren aufzurufen.  
  
-   C# lässt keine Nichttyp-Vorlagenparameter zu, wie z.B. `template C<int i> {}`.  
  
-   C# unterstützt keine explizite Spezialisierung; d.h. eine benutzerdefinierte Implementierung einer Vorlage für einen bestimmten Typ.  
  
-   C# unterstützt keine partielle Spezialisierung: Eine benutzerdefinierte Implementierung für eine Teilmenge der Typargumente.  
  
-   C# lässt nicht zu, dass der Typparameter als Basisklasse für den generischen Typ verwendet wird.  
  
-   C# lässt nicht zu, dass Typparameter über Standardtypen verfügen.  
  
-   In C# kann kein generischer Typparameter selbst generisch sein, obwohl konstruierte Typen als Generika verwendet werden können. C++ lässt Vorlagenparameter zu.  
  
-   C++ lässt Code zu, der möglicherweise nicht für alle Typparameter in der Vorlage gültig ist, die anschließend auf den spezifischen Typ, der als Typparameter verwendet wird, geprüft wird. In C# muss Code in einer Klasse in einer Weise geschrieben werden, dass er mit einem beliebigen Typ arbeiten kann, der die Einschränkungen erfüllt. Zum Beispiel kann in C++ eine Funktion geschrieben werden, die die arithmetischen Operatoren `+` und `-` für Objekte des Typparameters verwendet, was einen Fehler bei der Instanziierung der Vorlage mit einem Typ, der diese Operatoren nicht unterstützt, erzeugt. C# lässt dies zu; die einzigen zulässigen Sprachkonstrukte sind die, die von den Einschränkungen abgeleitet werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Vorlagen](https://docs.microsoft.com/cpp/cpp/templates-cpp)
