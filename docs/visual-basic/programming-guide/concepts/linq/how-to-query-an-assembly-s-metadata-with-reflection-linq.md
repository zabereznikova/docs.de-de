---
title: 'Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: b5b74e27d4cfeb4360d9c743d16c16dc82134038
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644663"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)
Das folgende Beispiel zeigt, wie LINQ mit Reflektion verwendet werden kann, um bestimmte Metadaten über Methoden abzurufen, die einem angegebenen Suchkriterium entsprechen. In diesem Fall findet die Abfrage die Namen aller Methoden in der Assembly, die aufzählbare Typen zurückgeben wie z.B. Arrays.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
Module Module1  
  
    Sub Main()  
        Dim asmbly As Assembly =   
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()   
                            Where type.IsPublic   
                            From method In type.GetMethods()   
                            Where method.ReturnType.IsArray = True   
                            Let name = method.ToString()   
                            Let typeName = type.ToString()   
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 Im Beispiel wird die <xref:System.Reflection.Assembly.GetTypes%2A>-Methode verwendet, um ein Array von Typen in der angegebenen Assembly zurückzugeben. Die [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md) Filter wird angewendet, sodass nur öffentliche Typen zurückgegeben werden. Für jeden öffentlichen Typ wird mit dem <xref:System.Reflection.MethodInfo>-Array eine Unterabfrage generiert, die vom <xref:System.Type.GetMethods%2A>-Aufruf zurückgegeben wird. Diese Ergebnisse werden gefiltert, damit nur die Methoden zurückgegeben werden, deren Rückgabetyp ein Array oder ein Typ ist, der <xref:System.Collections.Generic.IEnumerable%601> implementiert. Abschließend werden die Ergebnisse mithilfe des Typnamens als Schlüssel gruppiert.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und einer `Imports`-Anweisung für den System.Linq-Namespace.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
