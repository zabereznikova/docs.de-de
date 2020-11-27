---
title: 'Vorgehensweise: Verzögerte Initialisierung von Objekten'
description: Weitere Informationen finden Sie unter Ausführen einer verzögerten Initialisierung von Objekten mithilfe der System. Lazy- <T> Klasse. Verzögerte Initialisierung bedeutet, dass Objekte nicht erstellt werden, wenn Sie nicht benötigt werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
ms.openlocfilehash: 3de0d8ea8266931c2bcda5c59c1fef97602673d5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278127"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a>Vorgehensweise: Verzögerte Initialisierung von Objekten

Die <xref:System.Lazy%601?displayProperty=nameWithType>-Klasse vereinfacht die verzögerte Initialisierung und Instanziierung von Objekten. Beim verzögerten Initialisieren von Objekten können Sie die Erstellung vermeiden, wenn diese nie gebraucht werden, oder Sie können die Initialisierung verschieben, bis ein erster Zugriff erfolgt. Weitere Informationen finden Sie unter [Verzögerte Initialisierung](lazy-initialization.md).  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt, wie ein Wert mit <xref:System.Lazy%601> initialisiert wird. Gehen wir davon aus, dass die verzögerte Variable abhängig von anderem Code, der die `someCondition`-Variable auf TRUE oder FALSE festlegt, nicht gebraucht wird.  
  
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
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt, wie Sie die <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>-Klasse verwenden, um die Initialisierung eines Typs durchzuführen, der nur für die aktuelle Objektinstanz für den aktuellen Thread sichtbar ist.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [Verzögerte Initialisierung](lazy-initialization.md)
