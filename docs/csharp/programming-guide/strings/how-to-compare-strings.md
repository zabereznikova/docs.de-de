---
title: 'Gewusst wie: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 70bd8f52971115a36626961c2c605f2f93c1ae6b
ms.openlocfilehash: ed376960e0b3bb793b377cc8fac2fdefa030dcc0
ms.contentlocale: de-de
ms.lasthandoff: 09/19/2017

---
# <a name="how-to-compare-strings-c-programming-guide"></a>Gewusst wie: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch)

Wenn Sie Zeichenfolgen vergleichen, erzeugen Sie ein Ergebnis, das besagt, dass eine Zeichenfolge größer oder kleiner als eine andere ist oder dass die beiden Zeichenfolgen gleich sind. Die Regeln, nach denen das Ergebnis bestimmt wird, unterscheiden sich abhängig davon, ob Sie einen *Ordinalvergleich* oder einen *kulturabhängigen Vergleich* durchführen. Es ist wichtig, die richtige Art von Vergleich für eine bestimmte Aufgabe zu verwenden.

 Verwenden Sie grundlegende Ordinalvergleiche, wenn Sie die Werte zweier Zeichenfolgen vergleichen oder sortieren, ohne linguistische Konventionen zu berücksichtigen. Ein grundlegender ordinaler Vergleich (`System.StringComparison.Ordinal`) unterscheidet zwischen Groß- und Kleinschreibung, was bedeutet, dass die beiden Zeichenfolgen Zeichen für Zeichen übereinstimmen müssen: „and“ ist nicht gleich „And“ oder „AND“. Eine häufig verwendete Variante ist `System.StringComparison.OrdinalIgnoreCase`, bei der „and“, „And“ und „AND“ nicht unterschieden werden. `StringComparison.OrdinalIgnoreCase` wird häufig verwendet, um Dateinamen, Pfadnamen, Netzwerkpfade und jede andere Zeichenfolge, deren Wert basierend auf dem Gebietsschema des Computers des Benutzers nicht geändert wird, zu vergleichen. Weitere Informationen finden Sie unter <xref:System.StringComparison?displayProperty=fullName>.

 Kulturabhängige Vergleiche werden normalerweise verwendet, um Zeichenfolgen zu vergleichen und zu sortieren, die von Endbenutzern eingegeben werden, da die Zeichen und Sortierungskonventionen dieser Zeichenfolgen je nach Gebietsschema des Computers des Benutzers variieren können. Sogar Zeichenfolgen, die identische Zeichen enthalten, sortieren je nach Kultur des aktuellen Threads möglicherweise unterschiedlich.

> [!NOTE]
> Wenn Sie Zeichenfolgen vergleichen, sollten Sie die Methoden verwenden, die explizit angeben, welche Art von Vergleich Sie durchführen möchten. Dadurch kann der Code viel besser verwaltet und gelesen werden. Verwenden Sie wenn möglich die Überladungen der Methoden der Klassen <xref:System.String?displayProperty=fullName> und <xref:System.Array?displayProperty=fullName>, die den <xref:System.StringComparison>-Enumerationsparameter übernehmen, sodass Sie angeben können, welcher Vergleichstyp ausgeführt werden soll. Es empfiehlt sich, beim Vergleichen von Zeichenfolgen die Operatoren `==` und `!=` zu vermeiden. Vermeiden Sie es außerdem, die <xref:System.String.CompareTo%2A?displayProperty=fullName>-Instanzmethoden zu verwenden, da keine der Überladungen eine <xref:System.StringComparison> übernimmt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Zeichenfolgen, deren Werte sich basierend auf dem Gebietsschema des Computers des Benutzers nicht ändern, ordnungsgemäß verglichen werden. Darüber hinaus wird die Funktion von C# zur *Internalisierung von Zeichenfolgen* gezeigt. Wenn ein Programm zwei oder mehr identische Zeichenfolgenvariablen deklariert, speichert der Compiler alle am selben Speicherort. Durch Aufrufen der <xref:System.Object.ReferenceEquals%2A>-Methode können Sie sehen, dass die beiden Zeichenfolgen tatsächlich auf das gleiche Objekt im Arbeitsspeicher verweisen. Verwenden Sie die <xref:System.String.Copy%2A?displayProperty=fullName>-Methode, um die Internalisierung zu vermeiden, wie im Beispiel gezeigt.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Zeichenfolgen bevorzugt verglichen werden, indem die <xref:System.String?displayProperty=fullName>-Methoden verwendet werden, die eine <xref:System.StringComparison>-Enumeration übernehmen. Beachten Sie, dass die <xref:System.String.CompareTo%2A?displayProperty=fullName>-Instanzmethoden hier nicht verwendet werden, da keine der Überladungen eine <xref:System.StringComparison> übernimmt.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie Zeichenfolgen in einem Array auf kulturabhängige Weise mithilfe der statischen <xref:System.Array>-Methoden, die einen <xref:System.StringComparer?displayProperty=fullName>-Parameter akzeptieren, sortieren und danach suchen.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Auflistungsklassen wie <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> und <xref:System.Collections.Generic.List%601?displayProperty=fullName> verfügen über Konstruktoren, die einen <xref:System.StringComparer?displayProperty=fullName>-Parameter übernehmen, wenn der Typ des Elements oder der Schlüssel `string` ist. Im Allgemeinen sollten Sie nach Möglichkeit diese Konstruktoren verwenden und entweder `Ordinal` oder `OrdinalIgnoreCase` angeben.

## <a name="see-also"></a>Siehe auch
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Vergleichen von Zeichenfolgen](../../../standard/base-types/comparing.md)   
 [Globalisieren und Lokalisieren von Anwendungen](/visualstudio/ide/globalizing-and-localizing-applications)
