---
title: "Felder (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Felder [C#]"
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# Felder (C#-Programmierhandbuch)
Ein *Feld* ist eine Variable eines beliebigen Typs, die direkt in einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) deklariert wird.  Felder sind *Member* des Typs, der sie enthält.  
  
 Eine Klasse oder Struktur kann über Instanzfelder, statische Felder oder beides verfügen.  Instanzfelder sind für eine Instanz eines Typs spezifisch.  Wenn Sie eine Klasse "T" mit dem Instanzfeld "F" haben, können Sie zwei Objekte vom Typ "T" erstellen und den Wert von "F" in beiden Objekten ändern, ohne dabei den Wert im jeweils anderen Objekt zu ändern.  Im Gegensatz dazu gehört ein statisches Feld zur Klasse selbst und wird in allen Instanzen dieser Klasse bereitgestellt.  Durch die Instanz "A" vorgenommene Änderungen sind für die Instanzen "B" und "C" sofort sichtbar, wenn diese auf das Feld zugreifen.  
  
 Im Allgemeinen sollten Felder nur für Variablen verwendet werden, auf die privat oder geschützt zugegriffen werden kann.  Daten, die dem Clientcode von der Klasse verfügbar gemacht werden, sollten durch [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) und [Indexer](../../../csharp/programming-guide/indexers/index.md) bereitgestellt werden.  Mit diesen Konstrukten für indirekten Zugriff auf interne Felder können ungültige Eingabewerte verhindert werden.  Ein privates Feld, das über eine öffentliche Eigenschaft bereitgestellte Daten speichert, wird als *Sicherungsspeicher* oder *dahinter liegendes Feld* bezeichnet.  
  
 Felder speichern meist Daten, auf die von mehr als einer Klassenmethode zugegriffen werden muss und die über die Lebensdauer einer einzelnen Methode hinaus gespeichert werden müssen.  So könnte eine Klasse, die ein Kalenderdatum darstellt, drei Felder mit ganzzahligen Werten beinhalten, jeweils für den Tag, den Monat und das Jahr.  Variablen, die außerhalb des Bereichs einer einzelnen Methode nicht verwendet werden, sollten als *lokale Variablen* im Methodentext selbst deklariert werden.  
  
 Felder werden im Klassenblock definiert, indem die Zugriffsstufe des Felds, gefolgt vom Typ und dem Namen des Felds, angegeben wird.  Beispiele:  
  
 [!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/fields_1.cs)]  
  
 Um auf ein Feld in einem Objekt zuzugreifen, fügen Sie einen Punkt und den Feldnamen hinter dem Objektnamen hinzu, wie in `objectname.fieldname`.  Beispiele:  
  
 [!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/fields_2.cs)]  
  
 Bei der Deklaration eines Felds kann diesem mithilfe des Zuweisungsoperators ein Anfangswert zugewiesen werden.  Um dem `day`\-Feld zum Beispiel automatisch den Wert `"Monday"` zuzuweisen, deklarieren Sie `day` wie im folgenden Beispiel:  
  
 [!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/fields_3.cs)]  
  
 Felder werden sofort initialisiert, bevor der Konstruktor für die Objektinstanz aufgerufen wird.  Wenn der Konstruktor den Wert eines Felds zuweist, überschreibt er alle während der Felddeklaration angegebenen Werte.  Weitere Informationen finden Sie unter [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).  
  
> [!NOTE]
>  Ein Feldinitialisierer kann nicht auf andere Instanzfelder verweisen.  
  
 Felder können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected internal` gekennzeichnet werden.  Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Felder zugreifen können.  Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Ein Feld kann optional als [static](../../../csharp/language-reference/keywords/static.md) deklariert werden.  Dadurch ist das Feld jederzeit für die Aufrufer verfügbar, selbst wenn keine Instanz der Klasse vorhanden ist.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Ein Feld kann als [readonly](../../../csharp/language-reference/keywords/readonly.md) deklariert werden.  Einem schreibgeschützten Feld kann lediglich bei der Initialisierung oder in einem Konstruktor ein Wert zugewiesen werden.  Ein `static` `readonly`\-Feld ähnelt einer Konstante. Der einzige Unterschied besteht darin, dass der C\#\-Compiler während der Kompilierung keinen Zugriff auf den Wert hat, der in einem statischen schreibgeschützten Feld enthalten ist. Der Zugriff auf diesen Wert ist lediglich zur Laufzeit möglich.  Weitere Informationen finden Sie unter [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)