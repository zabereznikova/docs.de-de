---
title: "Gewusst wie: Abfangen einer Nicht-CLS-Ausnahme | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmen [C#], nicht mit CLS kompatibel"
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# Gewusst wie: Abfangen einer Nicht-CLS-Ausnahme
Einige .NET\-Sprachen, einschließlich C\+\+\/CLI, ermöglichen es Objekten, Ausnahmen auszulösen, die sich nicht von <xref:System.Exception> ableiten.  Diese Ausnahmen werden als *Nicht\-CLS\-Ausnahmen* oder *Nicht\-Ausnahmen* bezeichnet.  In [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] können Sie keine Nicht\-CLS\-Ausnahmen auslösen, sie aber auf zwei Weisen abfangen:  
  
-   Innerhalb eines `catch (Exception e)`\-Blocks als <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
     Standardmäßig fängt eine [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]\-Assembly Nicht\-CLS\-Ausnahmen als umschlossene Ausnahmen ab.  Verwenden Sie diese Methode, wenn Sie auf die ursprüngliche Ausnahme zugreifen müssen, die über die <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>\-Eigenschaft verfügbar ist.  Im Verfahren weiter unten in diesem Thema wird das Abfangen von Ausnahmen auf diese Weise beschrieben.  
  
-   Innerhalb eines allgemeinen catch\-Blocks \(eines catch\-Blocks, für den kein Ausnahmetyp angegeben wurde\), der nach einem `catch (Exception)`\-Block oder `catch (Exception e)`\-Block platziert wird.  
  
     Verwenden Sie diese Methode, wenn Sie Aktionen \(z. B. das Schreiben in eine Protokolldatei\) als Reaktion auf Nicht\-CLS\-Ausnahmen ausführen möchten und keinen Zugriff auf die Ausnahmeinformationen benötigen.  Standardmäßig umschließt die Common Language Runtime alle Ausnahmen.  Um dieses Verhalten zu deaktivieren, fügen Sie dem Code das folgende assemblyweit gültige Attribut hinzu, normalerweise in der Datei AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### So fangen Sie eine Nicht\-CLS\-Ausnahme ab  
  
1.  Verwenden Sie in einem `catch(Exception e) block` das `as`\-Schlüsselwort, um zu testen, ob `e` in eine <xref:System.Runtime.CompilerServices.RuntimeWrappedException> umgewandelt werden kann.  
  
2.  Greifen Sie auf die ursprüngliche Ausnahme über die <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>\-Eigenschaft zu.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine Nicht\-CLS\-Ausnahme abfangen, die von einer in C\+\+\/CLR geschriebenen Klassenbibliothek ausgelöst wurde.  Beachten Sie, dass in diesem Beispiel der [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]\-Clientcode den Ausnahmetyp im Voraus als <xref:System.String?displayProperty=fullName> identifiziert.  Sie können die <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>\-Eigenschaft wieder in ihren ursprünglichen Typ umwandeln, sofern auf diesen Typ über den Code zugegriffen werden kann.  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)