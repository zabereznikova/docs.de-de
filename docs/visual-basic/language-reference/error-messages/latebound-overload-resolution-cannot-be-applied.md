---
title: "Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30933"
  - "bc30933"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "overload resolution, with late-bound argument"
  - "BC30933"
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, doch der Verweis schlägt fehl, weil ein Argument vom Typ `Object` ist und der Datentyp des verweisenden Objekts eine Schnittstelle ist.  Das `Object`\-Argument erzwingt das Auflösen des Verweises durch den Compiler als spät gebundenen.  
  
 Unter diesen Bedingungen löst der Compiler die Überladung über die implementierende Klasse und nicht über die zugrunde liegende Schnittstelle auf.  Wenn die Klasse eine der überladenen Versionen umbenennt, behandelt der Compiler diese Version nicht als Überladung, da sie einen anderen Namen aufweist.  Dies wiederum bewirkt, dass der Compiler die umbenannte Version ignoriert, obwohl sie möglicherweise die richtige Version zum Auflösen des Verweises ist.  
  
 **Fehler\-ID:** BC30933  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie `CType`, um das Argument von `Object` in den Typ umzuwandeln, der durch die Signatur der aufzurufenden Überladung angegeben wird.  
  
     Beachten Sie, dass das Problem nicht durch Umwandeln des verweisenden Objekts in die zugrunde liegende Schnittstelle behoben wird.  Sie müssen das Argument umwandeln, um diesen Fehler zu vermeiden.  
  
## Beispiel  
 Im folgenden Beispiel wird der Aufruf einer überladenen `Sub`\-Prozedur veranschaulicht, die diesen Fehler zur Kompilierzeit verursacht.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 Wenn der Compiler im vorherigen Beispiel den Aufruf von `s1` entsprechend dem geschriebenen Code zulässt, erfolgt die Auflösung über die Klasse `c1` statt über die Schnittstelle `i1`.  Dies bedeutet, dass der Compiler `s2` nicht berücksichtigt, da sich ihr Name von `c1` unterscheidet, obwohl sie gemäß der Definition durch `i1` die richtige Version ist.  
  
 Sie können den Fehler beheben, indem Sie den Aufruf in eine der beiden folgenden Codezeilen ändern:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 In jeder der obigen Codezeilen wird die `Object`\-Variable `o1` explizit in einen der für Überladungen definierten Parametertypen umgewandelt.  
  
## Siehe auch  
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overload Resolution](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)