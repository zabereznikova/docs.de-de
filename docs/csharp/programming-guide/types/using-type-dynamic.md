---
title: Verwenden des Typs dynamic (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 7e2310df174a7c38fafba3fed4e4bd3de4fa377a
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="using-type-dynamic-c-programming-guide"></a>Verwenden des Typs dynamic (C#-Programmierhandbuch)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] führt einen neuen Typ ein, `dynamic`. Bei diesem Typ handelt es sich um einen statischen Typ. Ein Objekt des Typs `dynamic` umgeht aber die Überprüfung statischer Typen. In den meisten Fällen entspricht es der Funktionsweise des Typs `object`. Bei einem Element, das zur Kompilierzeit als `dynamic` typisiert wird, wird davon ausgegangen, dass es alle Vorgänge unterstützt. Daher müssen Sie sich keine Gedanken darüber machen, ob das Objekt seinen Wert von einer COM-API, einer dynamischen Sprache wie IronPython, vom HTML-DOM (Document Object Model), aus der Reflektion oder von einer anderen Quelle im Programm erhält. Wenn der Code jedoch nicht gültig ist, werden Fehler zur Laufzeit abgefangen.  
  
 Wenn z.B. die Instanzmethode `exampleMethod1` im folgenden Code nur einen Parameter hat, erkennt der Compiler, dass der erste Aufruf der Methode, `ec.exampleMethod1(10, 4)`, nicht gültig ist, da er zwei Argumente enthält. Dieser Aufruf löst einen Compilerfehler aus. Der zweite Aufruf der Methode, `dynamic_ec.exampleMethod1(10, 4)`, wird vom Compiler nicht überprüft, da der Typ von `dynamic_ec` `dynamic` ist. Daher wird kein Compilerfehler gemeldet. Allerdings bleibt der Fehler nicht unbegrenzt unbemerkt. Er wird zur Laufzeit abgefangen und führt zu einer Laufzeitausnahme.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]  
  
 In diesen Beispielen ist es die Rolle des Compilers, Informationen darüber zusammenzustellen, was jede Anweisung für die Behandlung des Objekts oder des Ausdrucks vorschlägt, die als `dynamic` typisiert sind. Die gespeicherten Informationen werden zur Laufzeit überprüft, und jede ungültige Anweisung verursacht eine Laufzeitausnahme.  
  
 Das Ergebnis der meisten dynamischen Vorgänge ist wiederum `dynamic`. Wenn Sie z.B. den Mauszeiger im folgenden Beispiel auf die Verwendung von `testSum` halten, zeigt IntelliSense den Typ **(local variable) dynamic testSum** an.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]  
  
 Vorgänge, in denen das Ergebnis nicht `dynamic` ist, enthalten Konvertierungen von `dynamic` in einen anderen Typ, und Konstruktoraufrufe, die Argumente vom Typ `dynamic` enthalten. In der folgende Deklaration ist der Typ von `testInstance` z.B. `ExampleClass`, nicht `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]  
  
 Im folgenden Abschnitt „Konvertierungen“ finden Sie Konvertierungsbeispiele.  
  
## <a name="conversions"></a>Konvertierungen  
 Konvertierungen zwischen dynamischen Objekten und anderen Typen sind sehr einfach. Dadurch kann der Entwickler zwischen dynamischem und nicht dynamischem Verhalten wechseln.  
  
 Jedes Objekt kann implizit zu einem dynamischen Typ konvertiert werden, wie in den folgenden Beispielen gezeigt.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]  
  
 Umgekehrt kann eine implizite Konvertierung dynamisch auf einen Ausdruck vom Typ `dynamic` angewendet werden.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]  
  
## <a name="overload-resolution-with-arguments-of-type-dynamic"></a>Überladungsauflösung mit Argumenten vom Typ „dynamic“  
 Überladungsauflösung erfolgt zur Laufzeit anstatt zur Kompilierzeit, wenn eines oder mehrere der Argumente in einem Methodenaufruf vom Typ `dynamic` sind, oder wenn der Empfänger des Methodenaufrufs vom Typ `dynamic` ist. Im folgenden Beispiel wird durch das Senden von `d1` als Argument kein Compilerfehler ausgelöst, wenn die einzige zugängliche `exampleMethod2`-Methode so definiert wird, dass sie ein Zeichenfolgenargument akzeptiert. Allerdings wird eine Laufzeitausnahme ausgelöst. Die Überladungsauflösung schlägt zur Laufzeit fehl, da der Laufzeittyp von `d1` `int` ist und `exampleMethod2` eine Zeichenfolge benötigt.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]  
  
## <a name="dynamic-language-runtime"></a>Dynamic Language Runtime  
 Die Dynamic Language Runtime (DLR) ist eine neue API in [!INCLUDE[net_v40_short](~/includes/net-v40-short-md.md)]. Sie bietet die Infrastruktur, die den Typ `dynamic` in C# und die Implementierung von dynamischen Programmiersprachen wie IronPython und IronRuby unterstützt. Weitere Informationen zur DLR finden Sie unter [Übersicht über die Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).  
  
## <a name="com-interop"></a>COM-Interop  
 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] enthält mehrere Funktionen, die die Benutzerfreundlichkeit bei Interoperationen mit COM-APIs wie den Automatisierungs-APIs in Microsoft Office verbessern. Zu diesen Verbesserungen gehören die Verwendung des Typs `dynamic` und von [benannten und optionalen Argumenten](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Viele COM-Methoden ermöglichen die Variation von Argument- und Rückgabetypen durch Festlegen der Typen als `object`. Dadurch wird das explizite Umwandeln der Werte für die Koordination mit stark typisierten Variablen in C# notwendig. Wenn Sie mit der Option [/link (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/link-compiler-option.md) kompilieren, ermöglicht es Ihnen die Einführung des Typs `dynamic`, das Vorkommen von `object` in COM-Signaturen so zu behandeln, als wäre es vom Typ `dynamic`. Dadurch können Sie einen Großteil der Umwandlung umgehen. Die folgenden Anweisungen unterscheiden z.B., wie Sie auf eine Zelle in einem Arbeitsblatt von Microsoft Office Excel mit dem Typ `dynamic` und ohne den Typ `dynamic` zugreifen.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Beschreibt die Verwendung des Schlüsselworts `dynamic`.|  
|[Übersicht über die Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)|Bietet eine Übersicht über die Dynamic Language Runtime (DLR), eine Laufzeitumgebung, die der Common Language Runtime (CLR) eine Reihe von Diensten für dynamische Sprachen hinzufügt.|  
|[Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|Bietet eine ausführliche Anleitung zum Erstellen eines benutzerdefinierten dynamischen Objekts und zum Erstellen eines Projekts, das auf eine `IronPython`-Bibliothek zugreift.|  
|[Gewusst wie: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Veranschaulicht, wie Sie ein Projekt erstellen, das benannte und optionale Argumente, den Typ `dynamic` und andere Verbesserungen verwendet, die den Zugriff auf Office-API-Objekte vereinfachen.|
