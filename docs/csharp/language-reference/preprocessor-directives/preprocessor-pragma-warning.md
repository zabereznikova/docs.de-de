---
title: "#pragma warning (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#pragma warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma warning [C#]"
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# #pragma warning (C#-Referenz)
`#pragma warning` kann bestimmte Warnungen aktivieren oder deaktivieren.  
  
## Syntax  
  
```  
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### Parameter  
 `warning-list`  
 Eine durch Trennzeichen getrennte Liste von Warnungsnummern.  Geben Sie die Zahlen allein ohne das "CS"\-Präfix ein.  
  
 Wenn keine Warnungsnummern angegeben sind, deaktiviert `disable` alle Warnungen, und `restore` aktiviert alle Warnungen.  
  
> [!NOTE]
>  Um die Nummern der Warnungen in Visual Studio zu suchen, erstellen Sie das Projekt, und suchen Sie dann nach den Warnungsnummern im Fenster **Ausgabe**.  
  
## Beispiel  
  
```  
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, 3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore 3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)