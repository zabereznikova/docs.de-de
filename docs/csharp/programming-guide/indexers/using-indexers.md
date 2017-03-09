---
title: "Verwenden von Indexern (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Indexer [C#], Informationen über Indexer"
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Verwenden von Indexern (C#-Programmierhandbuch)
Bei Indexern handelt es sich um ein syntaktisches Hilfsmittel, mit dem Sie [Klassen](../../../csharp/language-reference/keywords/class.md), [Strukturen](../../../csharp/language-reference/keywords/struct.md) und [Schnittstellen](../../../csharp/language-reference/keywords/interface.md) erstellen können, auf die Clientanwendungen wie auf ein Array zugreifen können.  Indexer werden am häufigsten in Typen implementiert, deren Hauptaufgabe darin besteht, eine interne Auflistung oder ein Array zu kapseln.  Nehmen Sie beispielsweise an, Sie haben eine Klasse mit dem Namen TempRecord zur Darstellung der Temperatur zu 10 verschiedenen Zeitpunkten während eines 24\-stündigen Zeitraums.  Die Klasse enthält ein Array mit dem Namen "temps" und dem float\-Datentyp zur Darstellung der Temperaturwerte sowie einen <xref:System.DateTime>\-Wert zur Darstellung der Zeitpunkte, zu denen die Temperaturen erfasst wurden.  Durch die Implementierung eines Indexers in dieser Klasse können Clients auf die Temperaturwerte in einer TempRecord\-Instanz als `float temp = tr[4]` statt als `float temp = tr.temps[4]` zugreifen.  Durch die Angabe des Indexers wird nicht nur die Syntax für Clientanwendungen vereinfacht, die Klasse und ihr Zweck werden darüber hinaus für andere Entwickler verständlicher.  
  
 Um einen Indexer für eine Klasse oder eine Struktur zu deklarieren, verwenden Sie das [this](../../../csharp/language-reference/keywords/this.md)\-Schlüsselwort wie in folgendem Beispiel:  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
  
```  
  
## Hinweise  
 Der Typ eines Indexers und der Typ seiner Parameter muss mindestens so gut zugänglich wie der Indexer selbst sein.  Weitere Informationen über Zugriffsebenen finden Sie unter [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Weitere Informationen zum Verwenden von Indexern mit einer Schnittstelle finden Sie unter [Schnittstellenindexer](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).  
  
 Die Signatur eines Indexers besteht aus der Anzahl und den Typen seiner formalen Parameter.  Sie umfasst nicht den Indexertyp oder die Namen der formalen Parameter.  Wenn Sie mehr als einen Indexer in derselben Klasse deklarieren, müssen diese verschiedene Signaturen aufweisen.  
  
 Ein Indexerwert wird nicht als Variable klassifiziert. Daher ist es nicht möglich, einen Indexerwert als [ref](../../../csharp/language-reference/keywords/ref.md)\-Parameter oder als [out](../../../csharp/language-reference/keywords/out.md)\-Parameter zu übergeben.  
  
 Verwenden Sie in der Deklaration ein `name`\-Attribut, um dem Indexer einen Namen zu geben, den andere Sprachen verwenden können.  Beispiele:  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 Dieser Indexer hat den Namen `TheItem`.  Wird das Namensattribut nicht bereitgestellt, wird `Item` zum Standardnamen.  
  
## Beispiel 1  
  
### Beschreibung  
 Das folgende Beispiel veranschaulicht die Deklaration des private\-Arrayfelds `temps` und eines Indexers.  Mit dem Indexer ist ein direkter Zugriff auf die `tempRecord[i]`\-Instanz möglich.  Alternativ zum Indexer können Sie das Array als [public](../../../csharp/language-reference/keywords/public.md)\-Member deklarieren und auf dessen Member `tempRecord.temps[i]` direkt zugreifen.  
  
 Beachten Sie, dass bei der Auswertung des Indexerzugriffs, z. B. in einer `Console.Write`\-Anweisung, der [get](../../../csharp/language-reference/keywords/get.md)\-Accessor aufgerufen wird.  Wenn kein `get`\-Accessor vorhanden ist, tritt daher während der Kompilierung ein Fehler auf.  
  
### Code  
 [!code-cs[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-indexers_1.cs)]  
  
## Indizieren mit anderen Werten  
 C\# beschränkt den Indextyp nicht auf eine ganze Zahl.  Zum Beispiel kann es nützlich sein, eine Zeichenfolge mit einem Indexer zu verwenden.  Ein solcher Indexer kann implementiert werden, indem in der Auflistung nach der Zeichenfolge gesucht und der richtige Wert zurückgegeben wird.  Da Accessoren überladen werden können, können die Zeichenfolgenversion und die ganzzahlige Version zusammen verwendet werden.  
  
## Beispiel 2  
  
### Beschreibung  
 In diesem Beispiel wird eine Klasse deklariert, die die Wochentage speichert.  Ein `get`\-Accessor wird deklariert, der eine Zeichenfolge und den Namen des Tages annimmt sowie den dazugehörigen ganzzahligen Wert zurückgibt.  Zum Beispiel gibt Sonntag 0 zurück, Montag gibt 1 zurück usw.  
  
### Code  
 [!code-cs[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-indexers_2.cs)]  
  
## Stabile Programmierung  
 Es gibt zwei grundlegende Möglichkeiten, mit denen die Sicherheit und die Zuverlässigkeit von Indexern verbessert werden kann:  
  
-   Bauen Sie einen Code zur Fehlerbehandlung für den Fall ein, dass Clientcode in einem ungültigen Indexwert übergeben wird.  Im ersten Beispiel in diesem Thema stellt die TempRecord\-Klasse eine Length\-Eigenschaft bereit, die eine Überprüfung der Eingabe durch den Clientcode vor Übergabe an den Indexer ermöglicht.  Sie können den Fehlerbehandlungscode auch in den Indexer selbst einfügen.  Dokumentieren Sie ausgelöste Ausnahmen in einem Indexeraccessor für Benutzer.  
  
-   Schränken Sie den Zugriff des `get`\-Accessors und des [set](../../../csharp/language-reference/keywords/set.md)\-Accessors so ein, dass die Beschränkung angemessen ist.  Insbesondere ist dies für den `set`\-Accessor wichtig.  Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)