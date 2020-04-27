---
title: Anzeigen von Typinformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: bf119ff547df59cd369d688fd81ab058893614f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130018"
---
# <a name="viewing-type-information"></a>Anzeigen von Typinformationen
Die Klasse <xref:System.Type?displayProperty=nameWithType> ist für die Reflektion wesentlich. Die Common Language Runtime (CLR) erstellt **Type** für einen geladenen Typ, wenn die Reflektion diesen anfordert. Sie können die Methoden, Felder, Eigenschaften und geschachtelten Klassen eines **Type**-Objekts dazu verwenden, alle Informationen zu diesem Typ zu erhalten.  
  
 Verwenden Sie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>, um **Type**-Objekte von Assemblys abzurufen, die nicht geladen wurden, und übergeben Sie den Namen des Typs oder der Typen, die Sie möchten. Verwenden Sie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, um **Type**-Objekte von Assemblys abzurufen, die bereits geladen wurden. Verwenden Sie <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>, um **Type**-Modulobjekte zu erhalten.  
  
> [!NOTE]
> Weitere Informationen zum Untersuchen und Bearbeiten generischer Typen und Methoden finden Sie in den Artikeln [Reflection and Generic Types (Reflektion und generische Typen)](reflection-and-generic-types.md) und [Vorgehensweise: Untersuchen und Instanziieren von generischen Typen mit Reflektion](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 In folgendem Beispiel wird die Syntax veranschaulicht, die für das Abrufen des <xref:System.Reflection.Assembly>-Objekts und -Moduls für eine Assembly erforderlich ist.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 In folgendem Beispiel wird das Abrufen eines **Type**-Objekts von einer geladenen Assembly veranschaulicht.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 Sobald Sie ein **Type**-Objekt abgerufen haben, gibt es viele Möglichkeiten, wie Sie Informationen zu den Membern des Typs erhalten können. Sie können z.B. alle Informationen zu den Membern des Typs erhalten, indem Sie die Methode <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> aufrufen, die ein Array von <xref:System.Reflection.MemberInfo>-Objekten abruft, die jeden Member des aktuellen Typs beschreiben.  
  
 Außerdem können Sie Methoden auf die **Type**-Klasse anwenden, um Informationen zu einem oder mehreren Konstruktoren, Methoden, Ereignissen, Felder oder Eigenschaften abzurufen, die Sie durch Namen angeben. <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> kapselt z.B. einen spezifischen Konstruktor für die aktuelle Klasse.  
  
 Wenn Sie ein **Type**-Objekt haben, können Sie die <xref:System.Type.Module%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um ein Objekt zu erhalten, das das Modul kapselt, das den Typ enthält. Verwenden Sie die <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType>-Eigenschaft, um ein Objekt zu finden, das die Assembly kapselt, die das Modul enthält. Sie können die Assembly, die den Typ kapselt, direkt mithilfe der <xref:System.Type.Assembly%2A?displayProperty=nameWithType>-Eigenschaft erhalten.  
  
## <a name="systemtype-and-constructorinfo"></a>System.Type und ConstructorInfo  
 In folgendem Beispiel wird veranschaulicht, wie Sie die Konstruktoren für eine Klasse auflisten können, in diesem Fall die Klasse <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a>MemberInfo, MethodInfo, FieldInfo und PropertyInfo  
 Rufen Informationen zu den Methoden, Eigenschaften, Ereignissen und Feldern eines Typs mithilfe der Objekte <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> und <xref:System.Reflection.PropertyInfo> ab.  
  
 In folgendem Beispiel wird das **MemberInfo**-Objekt verwendet, um die Anzahl von Membern in der **Klasse** aufzulisten. Zudem wird die <xref:System.Type.IsPublic%2A>-Eigenschaft verwendet, um die Sichtbarkeit der Klasse zu bestimmen.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 In folgendem Beispiel wird der Typ des angegeben Members untersucht. Es wird eine Reflektion für einen Member der Klasse **MemberInfo** ausgeführt, und deren Typ wird aufgelistet.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 Im folgenden Beispiel werden alle **\*Info**-Reflektionsklassen mit <xref:System.Reflection.BindingFlags> verwendet, um alle Member (Konstruktoren, Felder, Eigenschaften, Ereignisse und Methoden) der angegebenen Klasse aufzulisten. Dabei werden die Member in die Kategorien „Statisch“ und „Instanz“ aufgeteilt.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [Reflektion und generische Typen](reflection-and-generic-types.md)
