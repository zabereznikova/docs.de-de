---
title: "Destruktoren (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ [C#], In Destruktoren"
  - "C#-Sprache, Destruktoren"
  - "Destruktoren [C#]"
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Destruktoren (C#-Programmierhandbuch)
Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.  
  
## Hinweise  
  
-   Destruktoren können nicht in Strukturen definiert werden.  sie werden nur mit Klassen verwendet.  
  
-   Eine Klasse darf nur einen Destruktor besitzen.  
  
-   Destruktoren können nicht vererbt oder überladen werden.  
  
-   Destruktoren können nicht aufgerufen werden.  Der Aufruf wird automatisch vollzogen.  
  
-   Ein Destruktor akzeptiert weder Modifizierer, noch besitzt er Parameter.  
  
 Im Folgenden sehen Sie beispielsweise die Deklaration eines Destruktors für die `Car`\-Klasse:  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/destructors_1.cs)]  
  
 Der Destruktor ruft implizit <xref:System.Object.Finalize%2A> für die Basisklasse des Objekts auf.  Daher wird der vorige Destruktorcode implizit in den folgenden Code übersetzt:  
  
```  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 Auf diese Weise wird die `Finalize`\-Methode rekursiv für alle Instanzen in der Vererbungskette aufgerufen, und zwar von der am meisten bis zu der am wenigsten abgeleiteten Instanz.  
  
> [!NOTE]
>  Leere Destruktoren sollten nicht verwendet werden.  Wenn eine Klasse einen Destruktor enthält, wird ein Eintrag in der `Finalize`\-Warteschlange erstellt.  Wenn der Destruktor aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten.  Wenn der Destruktor leer ist, führt das lediglich zu einem unnötigen Leistungsverlust.  
  
 Der Programmierer kann nicht steuern, wann der Destruktor aufgerufen wird, da dies durch den Garbage Collector bestimmt wird.  Der Garbage Collector sucht nach Objekten, die von der Anwendung nicht mehr verwendet werden.  Wenn er ein Objekt findet, das entfernt werden könnte, ruft er den Destruktor \(wenn vorhanden\) auf und beansprucht den durch das Objekt belegten Speicherplatz.  Destruktoren werden darüber hinaus beim Beenden des Programms aufgerufen.  
  
 Es ist möglich, die Garbage Collection zu erzwingen, indem <xref:System.GC.Collect%2A> aufgerufen wird. Dieses Verfahren sollte jedoch möglichst vermieden werden, da es zu Leistungseinbußen führen kann.  
  
## Verwenden von Destruktoren zum Freigeben von Ressourcen  
 Im Allgemeinen erfordert C\# weniger Speicherverwaltung, als für die Entwicklung einer Sprache benötigt wird, die nicht auf eine Laufzeit mit Garbage Collection ausgerichtet ist.  Der Grund hierfür ist, dass der Garbage Collector von .NET Framework implizit die Belegung und Freigabe von Speicherplatz für Ihre Objekte verwaltet.  Wenn Ihre Anwendung jedoch nicht verwaltete Ressourcen kapselt, z. B. Fenster, Dateien und Netzwerkverbindungen, sollten Sie Destruktoren zur Freigabe der Ressourcen einsetzen.  Sobald das Objekt zerstört werden kann, führt der Garbage Collector die `Finalize`\-Methode des Objekts aus.  
  
## Explizite Freigabe von Ressourcen  
 Wenn Ihre Anwendung umfangreiche externe Ressourcen in Anspruch nimmt, empfiehlt es sich, unabhängig von der Freigabe des Objekts durch den Garbage Collector eine weitere Möglichkeit zur expliziten Freigabe der Ressourcen vorzusehen.  Sie können hierzu eine `Dispose`\-Methode von der <xref:System.IDisposable>\-Schnittstelle implementieren, die die erforderliche Bereinigung für das Objekt durchführt.  Dadurch kann die Leistung der Anwendung spürbar verbessert werden.  Auch bei Verwendung dieser expliziten Ressourcensteuerung stellt der Destruktor eine Absicherung zur Bereinigung der Ressourcen dar \(für den Fall, dass der Aufruf der `Dispose`\-Methode fehlschlägt\).  
  
 Weitere Informationen zur Bereinigung von Ressourcen finden Sie unter den folgenden Themen:  
  
-   [Cleaning Up Unmanaged Resources](../Topic/Cleaning%20Up%20Unmanaged%20Resources.md)  
  
-   [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)  
  
-   [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)  
  
## Beispiel  
 Im folgenden Beispiel werden drei Klassen erstellt, die eine Vererbungskette bilden.  Die `First`\-Klasse ist die Basisklasse, `Second` ist von `First` abgeleitet und `Third` von `Second`.  Alle drei Klassen besitzen Destruktoren.  In `Main()` wird eine Instanz der am meisten abgeleiteten Klasse erstellt.  Beachten Sie, dass die Destruktoren der drei Klassen bei Ausführung des Programms automatisch aufgerufen werden, und zwar in der Reihenfolge von der am meisten zu der am wenigsten abgeleiteten Klasse.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/destructors_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.IDisposable>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)