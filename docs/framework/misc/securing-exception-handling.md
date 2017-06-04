---
title: "Securing Exception Handling | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "code security, exception handling"
  - "security [.NET Framework], exception handling"
  - "secure coding, exception handling"
  - "exception handling, security"
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Securing Exception Handling
In Visual C\+\+ und in Visual Basic wird ein Filterausdruck an höherer Position im Stapel vor der **finally**\-Anweisung ausgeführt.  Der dem Filter zugewiesene **catch**\-Block wird nach der **finally**\-Anweisung ausgeführt.  Weitere Informationen finden Sie unter [Verwenden benutzergefilterter Ausnahmen](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).  In diesem Abschnitt werden die Auswirkungen dieser Reihenfolge auf die Sicherheit erläutert.  Sehen Sie sich das folgende Pseudocodebeispiel an, das die Reihenfolge der Ausführung von Filteranweisungen und **finally**\-Anweisungen veranschaulicht.  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 Dieser Code gibt Folgendes aus.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 Der Filter wird vor der **finally**\-Anweisung ausgeführt, sodass Sicherheitsprobleme durch alle Vorgänge entstehen können, die eine Änderung in einen Zustand bewirken können, in dem anderer Code ausgeführt werden kann.  Beispiel:  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 Dieser Pseudocode ermöglicht einem Filter an höherer Position im Stapel das Ausführen von beliebigem Code.  Weitere Beispiele für Operationen mit ähnlichen Auswirkungen sind der vorübergehende Identitätswechsel, das Festlegen eines internen Flags zum Umgehen einer Sicherheitsüberprüfung und das Ändern der dem Thread zugeordneten Kultur.  Als Lösung wird empfohlen, einen Ausnahmehandler einzuführen, um die Codeänderungen am Threadzustand von den Filterblöcken des Aufrufers zu isolieren.  Es ist jedoch unbedingt zu beachten, dass der Ausnahmehandler ordnungsgemäß eingeführt wird. Andernfalls wird dieses Problem nicht behoben.  Im folgenden Beispiel werden die benutzeroberflächenspezifischen Kultureinstellungen gewechselt. Alle Änderungen am Threadzustand können jedoch ebenso verfügbar gemacht werden.  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 Die richtige Lösung in diesem Fall ist das Umschließen des vorhandenen **try**\/**finally**\-Blocks mit einem **try**\/**catch**\-Block.  Das Problem wird nicht behoben, indem einfach eine **catch\-throw**\-Klausel in den vorhandenen **try**\/**finally**\-Block eingeführt wird, wie im folgenden Beispiel verdeutlicht wird.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 Das Problem wird dadurch nicht behoben, da die **finally**\-Anweisung vor der Übernahme der Kontrolle durch `FilterFunc` nicht ausgeführt wurde.  
  
 Im folgenden Beispiel wird das Problem behoben, indem sichergestellt wird, dass die **finally**\-Klausel ausgeführt wird, bevor an die Ausnahmefilterblöcke des Aufrufers eine Ausnahme ausgegeben wird.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)