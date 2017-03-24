---
title: 'Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c1bc26d7b23135dd45ad58ea0bd2510b7157448
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-query-an-assembly39s-metadata-with-reflection-linq-visual-basic"></a>Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)
Das folgende Beispiel zeigt, wie LINQ mit Reflektion verwendet werden kann, um angegebene Metadaten über Methoden abzurufen, die einem angegebenen Suchkriterium entsprechen. In diesem Fall findet die Abfrage die Namen aller Methoden in der Assembly, die enumerable-Typen, z. B. Arrays zurückgeben.  
  
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
  
 Im Beispiel wird die <xref:System.Reflection.Assembly.GetTypes%2A>Methode, um ein Array von Typen in der angegebenen Assembly zurückzugeben.</xref:System.Reflection.Assembly.GetTypes%2A> Die [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md) Filter wird angewendet, sodass nur öffentliche Typen zurückgegeben werden. Für jeden öffentlichen Typ wird eine Unterabfrage generiert, mit der <xref:System.Reflection.MethodInfo>von zurückgegebene Array die <xref:System.Type.GetMethods%2A>aufrufen.</xref:System.Type.GetMethods%2A> </xref:System.Reflection.MethodInfo> Diese Ergebnisse werden gefiltert, damit nur die Methoden zurückgegeben werden, deren Rückgabetyp ein Array oder ein Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> Abschließend werden die Ergebnisse mithilfe des Typnamens als Schlüssel gruppiert.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
