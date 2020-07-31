---
title: 'Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflexion (LINQ) (C#)'
description: Hier erfahren Sie, wie Sie LINQ mit Reflexions-APIs in C# verwenden können, um bestimmte Metadaten zu Methoden abzurufen, die einem Suchkriterium entsprechen.
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: dc5352e9cb90e9ad2808fb027823174d07d69da6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104589"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a>Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflexion (LINQ) (C#)

Die Reflektions-APIs von .NET können verwendet werden, um die Metadaten in einer .NET-Assembly zu untersuchen und Sammlungen von Typen, Typmembern, Parametern usw. zu erstellen, die sich in der Assembly befinden. Da diese Auflistungen die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützen, können sie mithilfe von LINQ abgefragt werden.  
  
Das folgende Beispiel zeigt, wie LINQ mit Reflektion verwendet werden kann, um bestimmte Metadaten über Methoden abzurufen, die einem angegebenen Suchkriterium entsprechen. In diesem Fall findet die Abfrage die Namen aller Methoden in der Assembly, die aufzählbare Typen zurückgeben wie z.B. Arrays.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
using System;
using System.Linq;
using System.Reflection;  

class ReflectionHowTO  
{  
    static void Main()  
    {  
        Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
        var pubTypesQuery = from type in assembly.GetTypes()  
                    where type.IsPublic  
                        from method in type.GetMethods()  
                        where method.ReturnType.IsArray == true
                            || ( method.ReturnType.GetInterface(  
                                typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                            && method.ReturnType.FullName != "System.String" )  
                        group method.ToString() by type.ToString();  

        foreach (var groupOfMethods in pubTypesQuery)  
        {  
            Console.WriteLine("Type: {0}", groupOfMethods.Key);  
            foreach (var method in groupOfMethods)  
            {  
                Console.WriteLine("  {0}", method);  
            }  
        }  

        Console.WriteLine("Press any key to exit... ");  
        Console.ReadKey();  
    }  
}
```  

Im Beispiel wird die <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>-Methode verwendet, um ein Array von Typen in der angegebenen Assembly zurückzugeben. Der [where](../../../language-reference/keywords/where-clause.md)-Filter wird angewendet, sodass nur öffentliche Typen zurückgegeben werden. Für jeden öffentlichen Typ wird mit dem <xref:System.Reflection.MethodInfo>-Array eine Unterabfrage generiert, die vom <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>-Aufruf zurückgegeben wird. Diese Ergebnisse werden gefiltert, damit nur die Methoden zurückgegeben werden, deren Rückgabetyp ein Array oder ein Typ ist, der <xref:System.Collections.Generic.IEnumerable%601> implementiert. Abschließend werden die Ergebnisse mithilfe des Typnamens als Schlüssel gruppiert.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (C#)](./linq-to-objects.md)
