---
title: Projektionsvorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: f76eeeb779ab08a575e758a9d974573b700ae652
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168335"
---
# <a name="projection-operations-c"></a>Projektionsvorgänge (C#)
Projektion bezieht sich auf einen Vorgang, bei dem ein Objekt in eine neue Form transformiert wird, die häufig nur aus den Eigenschaften besteht, die anschließend verwendet werden. Mithilfe der Projektion können Sie einen neuen Typ erstellen, der aus den einzelnen Objekten erstellt wird. Sie können eine Eigenschaft projizieren und eine mathematische Funktion für sie ausführen. Sie können auch das ursprüngliche Objekt projizieren, ohne es zu ändern.  
  
 Die Methoden des Standardabfrageoperators, die Projektion ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Auswählen|Projektwerte, die auf einer Transform-Funktion basieren.|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|SelectMany|Projiziert Sequenzen von Werten, die auf einer Transform-Funktion basieren, und fasst diese dann in eine Sequenz zusammen.|Mehrere `from`-Klauseln verwenden|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="select"></a>Auswählen  
 Im folgenden Beispiel wird die `select`-Klausel verwendet, um den ersten Buchstaben jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a>SelectMany  
 Im folgenden Beispiel wird die `from`-Klausel verwendet, um jedes Wort aus jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a>Select im Vergleich zu SelectMany  
 Die Arbeit von jeweils `Select()` und `SelectMany()` besteht darin, einen Ergebniswert (oder Werte) aus den Quellwerten zu erstellen. `Select()` generiert einen Ergebniswert für jeden Quellwert. Das Ergebnis ist daher eine Auflistung, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt. Im Gegensatz dazu erzeugt `SelectMany()` ein einziges Gesamtergebnis, das verkettete untergeordnete Auflistungen aus jedem Quellwert enthält. Die Transform-Funktion, die als Argument an `SelectMany()` übergeben wird, muss eine aufzählbare Sequenz von Werten für jeden Quellwert zurückgeben. Diese aufzählbaren Sequenzen werden anschließend von `SelectMany()` zu einer großen Sequenz verkettet.  
  
 Die folgenden zwei Abbildungen zeigen den konzeptionellen Unterschied zwischen den Aktionen der beiden Methoden. In jedem Fall wird davon ausgegangen, dass die Auswahlfunktion (Transform) das Array von Blumen aus jedem Quellwert auswählt.  
  
 Die Abbildung zeigt, wie `Select()` eine Auflistung zurückgibt, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.  
  
 ![Grafische Darstellung der Aktion Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 Diese Abbildung zeigt, wie `SelectMany()` die Zwischenmodus-Sequenz von Arrays in einem Endergebniswert verkettet, der jeden Wert aus jedem Zwischenmodus-Array enthält.  
  
 ![Grafische Darstellung der Aktion SelectMany&#40;&#41;](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a>Codebeispiel  
 Im folgenden Beispiel wird das Verhalten von `Select()` und `SelectMany()` verglichen. Der Code erstellt eine „Bouquet“ von Blumen, indem er die ersten beiden Elemente aus jeder Liste der Blumennamen in der Quellauflistung aufführt. In diesem Beispiel ist der „einzelne Wert“, den die Transformationsfunktion <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> verwendet, selbst eine Auflistung von Werten. Dies erfordert die zusätzliche `foreach`-Schleife, um jede Zeichenfolge in den einzelnen Untersequenzen aufzulisten.  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq>
- [Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md)
- [select-Klausel](../../../language-reference/keywords/select-clause.md)
- [Vorgehensweise: Auffüllen von Objektsammlungen mit Daten aus mehreren Quellen (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
