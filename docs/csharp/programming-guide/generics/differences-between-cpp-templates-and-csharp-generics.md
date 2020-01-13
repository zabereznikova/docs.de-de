---
title: Unterschiede zwischen C++-Vorlagen und C#-Generics – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
ms.openlocfilehash: e44f67353410c58c406620109270972df17f9f86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75703532"
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a>Unterschiede zwischen C++-Vorlagen und C#-Generics (C#-Programmierhandbuch)
C#-Generics und C++-Vorlagen sind Sprachfunktionen, die Unterstützung für parametrisierte Typen ermöglichen. Es gibt jedoch viele Unterschiede zwischen den beiden. Auf der Syntaxebene sind C#-Generics ein einfacherer Ansatz für parametrisierte Typen ohne die Komplexität von C++-Vorlagen. Darüber hinaus versucht C# nicht alle Funktionen bereitzustellen, die C++-Vorlagen bereitstellen. Auf der Ebene der Implementierung ist der wichtigste Unterschied, dass C#-Ersetzungen des generischen Typs zur Laufzeit durchgeführt werden und allgemeine Informationen für die instanziierten Objekte beibehalten werden. Weitere Informationen finden Sie unter [Generics zur Laufzeit](./generics-in-the-run-time.md).  
  
 Die folgenden sind die Hauptunterschiede zwischen C#-Generics und C++-Vorlagen:  
  
- C#-Generics bieten nicht die gleiche Menge an Flexibilität wie C++-Vorlagen. Es ist z.B. nicht möglich, arithmetische Operatoren in einer generischen Klasse von C# aufzurufen, obwohl es möglich ist, benutzerdefinierte Operatoren aufzurufen.  
  
- C# lässt keine Nichttyp-Vorlagenparameter zu, wie z.B. `template C<int i> {}`.  
  
- C# unterstützt keine explizite Spezialisierung; d.h. eine benutzerdefinierte Implementierung einer Vorlage für einen bestimmten Typ.  
  
- C# unterstützt keine partielle Spezialisierung: Eine benutzerdefinierte Implementierung für eine Teilmenge der Typargumente.  
  
- C# lässt nicht zu, dass der Typparameter als Basisklasse für den generischen Typ verwendet wird.  
  
- C# lässt nicht zu, dass Typparameter über Standardtypen verfügen.  
  
- In C# kann kein generischer Typparameter selbst generisch sein, obwohl konstruierte Typen als Generics verwendet werden können. C++ lässt Vorlagenparameter zu.  
  
- C++ lässt Code zu, der möglicherweise nicht für alle Typparameter in der Vorlage gültig ist, die anschließend auf den spezifischen Typ, der als Typparameter verwendet wird, geprüft wird. In C# muss Code in einer Klasse in einer Weise geschrieben werden, dass er mit einem beliebigen Typ arbeiten kann, der die Einschränkungen erfüllt. Zum Beispiel kann in C++ eine Funktion geschrieben werden, die die arithmetischen Operatoren `+` und `-` für Objekte des Typparameters verwendet, was einen Fehler bei der Instanziierung der Vorlage mit einem Typ, der diese Operatoren nicht unterstützt, erzeugt. C# lässt dies zu; die einzigen zulässigen Sprachkonstrukte sind die, die von den Einschränkungen abgeleitet werden können.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Einführung in Generics](./index.md)
- [Vorlagen](/cpp/cpp/templates-cpp)
