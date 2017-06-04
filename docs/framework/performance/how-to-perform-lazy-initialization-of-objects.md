---
title: "How to: Perform Lazy Initialization of Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lazy initialization in .NET, how to perform"
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Perform Lazy Initialization of Objects
Die <xref:System.Lazy%601?displayProperty=fullName>\-Klasse vereinfacht die verzögerte Initialisierung und Instanziierung von Objekten.  Wenn Sie Objekte verzögert initialisieren, müssen Sie die Objekte ggf. gar nicht erstellen, falls sie nie benötigt werden, oder Sie können ihre Initialisierung bis zum ersten Zugriff verschieben.  Weitere Informationen finden Sie unter [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Beispiel  
 Im folgenden Beispiel wird das Initialisieren eines Werts mit <xref:System.Lazy%601> gezeigt.  In diesem Beispiel wird angenommen, dass die verzögerte Variable abhängig von anderem Code, durch den die `someCondition`\-Variable auf true oder false festgelegt wird, möglicherweise nicht benötigt wird.  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
{  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Threading.ThreadLocal%601?displayProperty=fullName>\-Klasse zum Initialisieren eines Typs gezeigt, der nur für die aktuelle Objektinstanz im aktuellen Thread sichtbar ist.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## Siehe auch  
 <xref:System.Threading.LazyInitializer?displayProperty=fullName>   
 [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md)