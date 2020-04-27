---
title: 'Vorgehensweise: Laden von Assemblys in den auf Reflektion beschränkten Kontext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: cac6b3b3adf070ad6070e5c5941653f20dedd907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130102"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a>Vorgehensweise: Laden von Assemblys in den auf Reflektion beschränkten Kontext

Mit dem ReflectionOnly-Load-Kontext können Sie Assemblys untersuchen, die für andere Plattformen oder andere Versionen von .NET Framework kompiliert wurden. In diesen Kontext geladener Code kann nur untersucht werden. Er kann nicht ausgeführt werden. Dies bedeutet, dass keine Objekte erstellt werden können, weil Konstruktoren nicht ausgeführt werden können. Da der Code nicht ausgeführt werden kann, werden Abhängigkeiten nicht automatische geladen. Wenn Sie diese untersuchen möchten, müssen Sie sie selbst laden.

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a>So können Sie eine Assembly in den ReflectionOnly-Kontext laden

1. Verwenden Sie die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29>-Methodenüberladung, um die Assembly mit deren Anzeigenamen zu laden, oder die <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>-Methode, um die Assembly mit deren Pfad zu laden. Wenn die Assembly ein binäres Image ist, verwenden Sie die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>-Methodenüberladung.

    > [!NOTE]
    > Sie können den ReflectionOnly-Kontext nicht zum Laden einer Version von „mscorlib.dll“ aus einer Version von .NET Framework verwenden, wenn sich diese Version von der Version des Ausführungskontexts unterscheidet.

2. Wenn die Assembly Abhängigkeiten hat, werden diese von der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>-Methode nicht geladen. Wenn Sie diese untersuchen möchten, müssen Sie sie selbst laden.

3. Sie können mit der <xref:System.Reflection.Assembly.ReflectionOnly%2A>-Eigenschaft einer Assembly feststellen, ob die Assembly in einen ReflectionOnly-Kontext geladen wurde.

4. Wenn Attribute auf die Assembly oder auf Typen in der Assembly angewendet wurden, können Sie sich diese Attribute mit der <xref:System.Reflection.CustomAttributeData>-Klasse anschauen, um sicherzustellen, dass der Code nicht im ReflectionOnly-Kontext ausgeführt wird. Verwenden Sie die entsprechende Überladung der <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>-Methode, um <xref:System.Reflection.CustomAttributeData>-Objekte zu erhalten, die die auf eine Assembly, einen Member, ein Modul oder einen Parameter angewendeten Attribute darstellen.

    > [!NOTE]
    > Auf die Assembly oder auf deren Inhalte angewendete Attribute sind möglicherweise in der Assembly oder in einer anderen in den ReflectionOnly-Kontext geladenen Assembly definiert. Es ist nicht möglich, im Voraus zu bestimmen, wo die Attribute definiert sind.

## <a name="example"></a>Beispiel

In folgendem Codebeispiel wird veranschaulicht, wie Sie die Attribute, die auf eine in den ReflectionOnly-Kontext geladene Assembly angewendet wurden, untersuchen können.

Im Codebeispiel wird ein benutzerdefiniertes Attribut mit zwei Konstruktoren und einer Eigenschaft definiert. Das Attribut wird auf die Assembly angewendet sowie auf einen in der Assembly deklarierten Typ, eine Methode dieses Typs und einen Parameter der Methode. Bei der Ausführung lädt die Assembly sich selbst in den ReflectionOnly-Kontext und zeigt Informationen zu den benutzerdefinierten Attributen an, die auf die Assembly und die Typen und Member, die sie enthält, angewendet wurden.

> [!NOTE]
> Um das Codebeispiel einfacher zu halten, lädt und untersucht die Assembly sich selbst. Für gewöhnlich ist nicht zu erwarten, dass die gleiche Assembly sowohl in den Ausführungskontext und den ReflectionOnly-Kontext geladen wird.

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
