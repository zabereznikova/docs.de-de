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
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a><span data-ttu-id="87baa-103">Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflexion (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="87baa-103">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>

<span data-ttu-id="87baa-104">Die Reflektions-APIs von .NET können verwendet werden, um die Metadaten in einer .NET-Assembly zu untersuchen und Sammlungen von Typen, Typmembern, Parametern usw. zu erstellen, die sich in der Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="87baa-104">The .NET reflection APIs can be used to examine the metadata in a .NET assembly and create collections of types, type members, parameters, and so on that are in that assembly.</span></span> <span data-ttu-id="87baa-105">Da diese Auflistungen die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützen, können sie mithilfe von LINQ abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="87baa-105">Because these collections support the generic <xref:System.Collections.Generic.IEnumerable%601> interface, they can be queried by using LINQ.</span></span>  
  
<span data-ttu-id="87baa-106">Das folgende Beispiel zeigt, wie LINQ mit Reflektion verwendet werden kann, um bestimmte Metadaten über Methoden abzurufen, die einem angegebenen Suchkriterium entsprechen.</span><span class="sxs-lookup"><span data-stu-id="87baa-106">The following example shows how LINQ can be used with reflection to retrieve specific metadata about methods that match a specified search criterion.</span></span> <span data-ttu-id="87baa-107">In diesem Fall findet die Abfrage die Namen aller Methoden in der Assembly, die aufzählbare Typen zurückgeben wie z.B. Arrays.</span><span class="sxs-lookup"><span data-stu-id="87baa-107">In this case, the query will find the names of all the methods in the assembly that return enumerable types such as arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87baa-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87baa-108">Example</span></span>  
  
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

<span data-ttu-id="87baa-109">Im Beispiel wird die <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>-Methode verwendet, um ein Array von Typen in der angegebenen Assembly zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="87baa-109">The example uses the <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> method to return an array of types in the specified assembly.</span></span> <span data-ttu-id="87baa-110">Der [where](../../../language-reference/keywords/where-clause.md)-Filter wird angewendet, sodass nur öffentliche Typen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="87baa-110">The [where](../../../language-reference/keywords/where-clause.md) filter is applied so that only public types are returned.</span></span> <span data-ttu-id="87baa-111">Für jeden öffentlichen Typ wird mit dem <xref:System.Reflection.MethodInfo>-Array eine Unterabfrage generiert, die vom <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>-Aufruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="87baa-111">For each public type, a subquery is generated by using the <xref:System.Reflection.MethodInfo> array that is returned from the <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> call.</span></span> <span data-ttu-id="87baa-112">Diese Ergebnisse werden gefiltert, damit nur die Methoden zurückgegeben werden, deren Rückgabetyp ein Array oder ein Typ ist, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.</span><span class="sxs-lookup"><span data-stu-id="87baa-112">These results are filtered to return only those methods whose return type is an array or else a type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="87baa-113">Abschließend werden die Ergebnisse mithilfe des Typnamens als Schlüssel gruppiert.</span><span class="sxs-lookup"><span data-stu-id="87baa-113">Finally, these results are grouped by using the type name as a key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87baa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87baa-114">See also</span></span>

- [<span data-ttu-id="87baa-115">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="87baa-115">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
