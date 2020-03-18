---
title: Eigenschaften – C#-Programmierhandbuch
ms.date: 03/10/2017
f1_keywords:
- cs.properties
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
ms.openlocfilehash: ee530e981e0c85302b2b11cc739d6c51d6650ddd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170103"
---
# <a name="properties-c-programming-guide"></a>Eigenschaften (C#-Programmierhandbuch)

Eine Eigenschaft ist ein Member, das einen flexiblen Mechanismus zum Lesen, Schreiben oder Berechnen des Werts eines privaten Felds bietet. Eigenschaften können wie öffentliche Datenmember verwendet werden, es sind jedoch spezielle Methoden namens *Accessoren*. Dies ermöglicht den problemlosen Datenzugriff und unterstützt weiterhin die Sicherheit und Flexibilität der Methoden.  

## <a name="properties-overview"></a>Übersicht über Eigenschaften  
  
- Mithilfe von Eigenschaften kann eine Klasse eine öffentliche Methode zum Abrufen und Festlegen von Werten verfügbar machen und dabei den Implementierungs- oder Verifizierungscode ausblenden.  
  
- Ein [get](../../language-reference/keywords/get.md) -Eigenschaftenaccessor wird verwendet, um den Wert der Eigenschaft zurückzugeben. Ein [set](../../language-reference/keywords/set.md) -Eigenschaftenaccessor wird verwendet, um einen neuen Wert zuzuweisen. Diese Zugriffsmethoden können über verschiedene Zugriffsebenen verfügen. Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](./restricting-accessor-accessibility.md).  
  
- Das [value](../../language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Accessor zugewiesen wird.  
- Eigenschaften können sein: *Lesen/Schreiben* (beide verfügen über einen `get`- und `set`-Accessor), *schreibgeschützt* (verfügen über einen `get`-Accessor, jedoch keinen `set`-Accessor), oder *lesegeschützt* (verfügen über einen `set`-Accessor, jedoch keinen `get` Accessor). Lesegeschützte Eigenschaften sind selten und werden am häufigsten verwendet, um den Zugriff auf vertrauliche Daten einzuschränken.

- Einfache Eigenschaften, die keinen benutzerdefinierten Accessorcode erfordern können implementiert werden, entweder als Ausdruckstextdefinitionen oder als [automatisch implementierte Eigenschaften](./auto-implemented-properties.md).

## <a name="properties-with-backing-fields"></a>Eigenschaften mit Unterstützungsfeldern

Ein grundlegendes Muster zum Implementieren einer Eigenschaft umfasst ein privates Unterstützungsfeld zum Festlegen und Abrufen des Eigenschaftswerts. Der `get`-Accessor gibt den Wert des privaten Felds zurück, und der `set`-Accessor kann die Validierung einiger Daten ausführen, bevor er dem privaten Feld einen Wert zuweist. Beide Accessoren führen möglicherweise eine Konvertierung oder eine Berechnung der Daten aus, bevor sie gespeichert oder zurückgegeben werden.

Dieses Muster wird anhand des folgenden Beispiels veranschaulicht. In diesem Beispiel stellt die `TimePeriod`-Klasse ein Zeitintervall dar. Intern speichert die Klasse das Zeitintervall in Sekunden in einem privaten Feld mit dem Namen `_seconds`. Eine Schreib-Lese-Eigenschaft mit dem Namen `Hours` ermöglicht dem Kunden, das Zeitintervall in Stunden anzugeben. Die `get`- und `set`-Accessoren führen jeweils die notwendige Konvertierung zwischen Stunden und Sekunden durch. Darüber hinaus prüft der `set`-Accessor die Daten, und löst eine <xref:System.ArgumentOutOfRangeException> aus, wenn die Anzahl von Stunden ungültig ist.

 [!code-csharp[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]  
  
## <a name="expression-body-definitions"></a>Ausdruckstextdefinitionen  

 Häufig bestehen Eigenschaftenaccessoren aus einzeilige Anweisungen, die gerade das Ergebnis eines Ausdrucks zuweisen oder zurückgeben. Sie können diese Eigenschaften als Ausdruckskörpermember implementieren. Ausdruckstextdefinitionen bestehen aus dem `=>`-Symbol, gefolgt von dem Ausdruck, der der Eigenschaft zugewiesen oder aus dieser abgerufen werden soll.

 Beginnend mit dem C# 6, können schreibgeschützte Eigenschaften den `get`-Accessor als Ausdruckskörpermember implementieren. In diesem Fall werden weder das `get`-Accessorschlüsselwort noch das `return`-Schlüsselwort verwendet. Das folgende Beispiel implementiert die schreibgeschützte `Name`-Eigenschaft als ein Ausdruckskörpermember.

 [!code-csharp[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]  

 Ab C# 7.0 können sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert werden. In diesem Fall müsse die `get`- und `set`-Schlüsselwörter vorhanden sein. Das folgende Beispiel veranschaulicht die Verwendung von Ausdruckstextdefinitionen für beide Accessoren. Beachten Sie, dass das `return`-Schlüsselwort nicht mit dem `get`-Accessor verwendet wird.

  [!code-csharp[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]  

## <a name="auto-implemented-properties"></a>Automatisch implementierte Eigenschaften

In einigen Fällen weisen die Eigenschaft `get`- und `set`-Accessoren nur einen Wert zu oder rufen einen Wert aus einem Unterstützungsfeld ab, ohne zusätzliche Logik. Mithilfe von automatisch implementierten Eigenschaften können Sie Ihren Code vereinfachen, während der C#-Compiler das Unterstützungsfeld für Sie transparent bereitstellt.

Wenn eine Eigenschaft jeweils über einen `get`- und `set`-Accessor verfügt, müssen beide automatisch implementiert werden. Definieren Sie eine automatisch implementierte Eigenschaft mithilfe der `get`- und `set`-Schlüsselwörter ohne jede Implementierung. Im folgenden Beispiel wird das vorherige Beispiel wiederholt, außer das `Name` und `Price` automatisch implementierte Eigenschaften sind. Beachten Sie, dass das Beispiel auch den parametrisierten Konstruktor entfernt, damit `SaleItem`-Objekte jetzt mit einem Aufruf des parameterlosen Konstruktors und eines [Objektinitialisierers](object-and-collection-initializers.md) initialisiert werden.

  [!code-csharp[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]  

## <a name="related-sections"></a>Verwandte Abschnitte  
  
- [Verwenden von Eigenschaften](./using-properties.md)  
  
- [Schnittstelleneigenschaften](./interface-properties.md)  
  
- [Vergleich zwischen Eigenschaften und Indexern](../indexers/comparison-between-properties-and-indexers.md)  
  
- [Einschränken des Zugriffsmethodenzugriffs](./restricting-accessor-accessibility.md)  
  
- [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen finden Sie unter [Eigenschaften](~/_csharplang/spec/classes.md#properties) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Verwenden von Eigenschaften](./using-properties.md)
- [Indexer](../indexers/index.md)
- [get-Schlüsselwort](../../language-reference/keywords/get.md)
- [set-Schlüsselwort](../../language-reference/keywords/set.md)
