---
title: Generika (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
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
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: de81058173b0985577474e8601aa84d4e83336a5
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---
# <a name="generics-c-programming-guide"></a>Generika (C#-Programmierhandbuch)
Generika wurden zur Version 2.0 der Sprache C# und der Common Language Runtime (CLR) hinzugefügt. Generika führen in .NET Framework das Konzept der Typparameter ein, wodurch Sie Klassen und Methoden entwerfen können, die die Spezialisierung einer oder mehr Typen verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird. Indem Sie z.B. einen generischen Parameter „T“ verwenden, können Sie eine einzelne Klasse schreiben, die anderer Clientcode verwenden kann, ohne die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen einzugehen, wie folgendermaßen gezeigt wird:  
  
 [!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a>Übersicht über Generika  
  
-   Verwenden Sie Generika, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.  
  
-   Generika werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.  
  
-   Die Klassenbibliothek von .NET Framework enthält eine Reihe generischer Auflistungsklassen im <xref:System.Collections.Generic>-Namespace. Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.  
  
-   Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.  
  
-   Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.  
  
-   Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:   
  
-   [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [Vorteile von Generika](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [Generische Typparameter](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [Generische Schnittstellen](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [Generische Delegate](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [Unterschiede zwischen C++-Vorlagen und C#-Generika](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [Generika und Reflexion](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [Generika in der .NET Framework-Klassenbibliothek](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)   
 [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)

