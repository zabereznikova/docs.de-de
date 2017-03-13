---
title: "lock-Anweisung (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "lock_CSharpKeyword"
  - "lock"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lock-Schlüsselwort [C#]"
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# lock-Anweisung (C#-Referenz)
Das `lock`\-Schlüsselwort kennzeichnet einen Anweisungsblock als kritischen Abschnitt, indem die Sperre für gegenseitigen Ausschluss eines bestimmten Objekts ermittelt, eine Anweisung ausgeführt und die Sperre wieder aufgehoben wird.  Das folgende Beispiel enthält eine `lock`\-Anweisung.  
  
```  
  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
  
```  
  
 Weitere Informationen finden Sie unter [Threadsynchronisierung](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Hinweise  
 Mit dem `lock`\-Schlüsselwort wird sichergestellt, dass ein Thread nicht auf einen kritischen Abschnitt des Codes zugreift, während ein anderer Thread mit diesem Codeabschnitt befasst ist.  Wenn ein anderer Thread versucht, auf gesperrten Code zuzugreifen, wartet er bis zur Freigabe des Objekts \(Blockierung\).  
  
 Im Abschnitt [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md) wird das Threading beschrieben.  
  
 Das `lock`\-Schlüsselwort ruft <xref:System.Threading.Monitor.Enter%2A> am Anfang des Blocks und <xref:System.Threading.Monitor.Exit%2A> am Ende des Blocks auf.  <xref:System.Threading.ThreadInterruptedException> wird ausgelöst, wenn <xref:System.Threading.Thread.Interrupt%2A> einen Thread unterbrochen wird, der wartet, eine `lock`\-Anweisung einzugeben.  
  
 Vermeiden Sie es grundsätzlich, einen `public`\-Typ zu sperren oder Instanzen, die nicht durch Ihren Code gesteuert werden.  Die allgemeinen Konstrukte `lock (this)`, `lock (typeof (MyType))` und `lock ("myLock")` verstoßen gegen diese Richtlinie:  
  
-   `lock (this)` ist problematisch, wenn auf die Instanz öffentlich zugegriffen werden kann.  
  
-   `lock (typeof (MyType))` ist problematisch, wenn `MyType` öffentlich zugreifbar ist.  
  
-   `lock("myLock")` ist problematisch, weil jeder andere Code in diesem Prozess, der dieselbe Zeichenfolge verwendet, von derselben Sperre betroffen ist.  
  
 Es wird empfohlen, ein `private`\-Objekt zu definieren, das gesperrt werden soll, oder eine `private static`\-Objektvariable, um Daten zu schützen, die alle Instanzen gemeinsam nutzen.  
  
 Sie können das [Sie erwarten](../../../csharp/language-reference/keywords/await.md)\-Schlüsselwort im Text einer `lock`\-Anweisung verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird eine einfache Verwendung von Threads ohne Sperren in C\# dargestellt:  
  
 [!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## Beispiel  
 Im folgenden Beispiel werden Threads und `lock` verwendet.  Solange die `lock`\-Anweisung vorhanden ist, stellt der Anweisungsblock einen kritischen Abschnitt dar, und `balance` wird nie zu einer negativen Zahl.  
  
 [!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Reflection.MethodImplAttributes>   
 <xref:System.Threading.Mutex>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md)   
 [Monitore](../Topic/Monitors.md)   
 [Interlocked Operations](../Topic/Interlocked%20Operations.md)   
 [AutoResetEvent](../Topic/AutoResetEvent.md)   
 [Threadsynchronisierung](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)