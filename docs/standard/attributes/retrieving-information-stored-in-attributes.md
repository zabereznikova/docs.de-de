---
title: Abrufen von Informationen aus Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
ms.openlocfilehash: 4f0f3555ae1ab7e662d5f88ac65739a7c791a964
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78158076"
---
# <a name="retrieving-information-stored-in-attributes"></a>Abrufen von Informationen aus Attributen
Das Abrufen eines benutzerdefinierten Attributs ist ein einfacher Prozess. Zuerst deklarieren Sie eine Instanz des Attributs, das Sie abrufen möchten. Dann verwenden Sie die <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>-Methode, um das neue Attribut auf den Wert des abzurufenden Attributs zu initialisieren. Sobald das neue Attribut initialisiert wurde, verwenden Sie einfach dessen Eigenschaften, um die Werte abzurufen.  
  
> [!IMPORTANT]
> In diesem Thema wird beschrieben, wie Attribute für Code abgerufen werden, der in den Ausführungskontext geladen wird. Zum Abrufen von Attributen für Code, der in den reflektionsbezogenen Kontext geladen wurde, müssen Sie die <xref:System.Reflection.CustomAttributeData>-Klasse verwenden, wie in [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) beschrieben.  
  
 Dieser Abschnitt erläutert die folgenden Möglichkeiten zum Abrufen von Attributen:  
  
- [Eine einzelne Instanz eines Attributs abrufen](#cpconretrievingsingleinstanceofattribute)  
  
- [Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
- [Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Abrufen einer einzelnen Instanz eines Attributs  
 Im folgenden Beispiel wird die (im vorherigen Abschnitt beschriebene) `DeveloperAttribute`-Klasse auf die `MainApp`-Klasse auf Klassenebene angewendet. Die `GetAttribute`-Methode verwendet **GetCustomAttribute**, um die in `DeveloperAttribute` gespeicherten Werte auf Klassenebene abzurufen, bevor sie in der Konsole angezeigt werden.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Dieses Programm zeigt folgenden Text bei der Ausführung an.  
  
```console  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Wenn das Attribut nicht gefunden wird, initialisiert die **GetCustomAttribute**-Methode `MyAttribute` auf einen Nullwert. In diesem Beispiel wird `MyAttribute` auf eine solche Instanz geprüft und der Benutzer benachrichtigt, wenn kein Attribut gefunden wird. Wenn das `DeveloperAttribute` nicht im Klassenbereich gefunden werden, wird die folgende Meldung in der Konsole angezeigt.  
  
```console  
The attribute was not found.
```  
  
 In diesem Beispiel wird davon ausgegangen, dass sich die Attributdefinition im aktuellen Namespace befindet. Denken Sie daran, den Namespace zu importieren, in dem sich die Attributdefinition befindet, wenn diese nicht im aktuellen Namespace ist.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet  
 Im vorherigen Beispiel werden die zu prüfende Klasse und das zu suchenden spezifische Attribut an <xref:System.Attribute.GetCustomAttribute%2A> übergeben. Dieser Code funktioniert gut, wenn nur eine Instanz eines Attributs auf Klassenebene angewendet wird. Wenn jedoch mehrere Instanzen eines Attributs auf derselben Klassenebene angewendet werden, ruft die **GetCustomAttribute**-Methode nicht alle Informationen ab. In Fällen, in dem mehrere Instanzen des gleichen Attributs in demselben Gültigkeitsbereich angewendet werden, können Sie mithilfe von <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> alle Instanzen eines Attributs in einem Array platzieren. Wenn beispielsweise zwei Instanzen von `DeveloperAttribute` auf Klassenebene derselben Klasse angewendet werden, kann die `GetAttribute`-Methode zum Anzeigen der in beiden Attributen gefundenen Informationen geändert werden. Beim Anwenden mehrerer Attribute auf derselben Ebene müssen Sie beachten, dass das Attribut mit der **AllowMultiple**-Eigenschaft definiert wird, die in der **auf**true<xref:System.AttributeUsageAttribute> gesetzt ist.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der **GetCustomAttributes**-Methode ein Array erstellen, das auf alle Instanzen von `DeveloperAttribute` in einer bestimmten Klasse verweist. Die Werte aller Attribute werden anschließend in der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Wenn keine Attribute gefunden werden, gibt dieser Code eine Warnung an den Benutzer aus. Andernfalls werden die in beiden Instanzen von `DeveloperAttribute` enthaltenen Informationen angezeigt.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet  
 Die Methoden <xref:System.Attribute.GetCustomAttributes%2A> und <xref:System.Attribute.GetCustomAttribute%2A> durchsuchen nicht eine ganze Klasse, um Instanzen eines Attributs in dieser Klasse zurückzugeben. Stattdessen suchen sie nur nach einer bestimmten Methode oder einem bestimmten Element zu einem gegebenen Zeitpunkt. Angenommen, Sie haben eine Klasse, für die das gleiche Attribut auf jedes Element angewendet wurde. Um nun die Werte in den Attributen abzurufen, die auf diese Elemente angewendet wurden, müssen Sie jede Methode oder jedes Element einzeln für **GetCustomAttributes** und  **GetCustomAttribute** bereitstellen.  
  
 Im folgenden Codebeispiel wird eine Klasse als Parameter akzeptiert und nach dem `DeveloperAttribute` (zuvor definiert) auf Klassenebene und in jeder einzelnen Methode dieser Klasse gesucht.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Wenn auf Methoden- oder Klassenebene keine Instanzen von `DeveloperAttribute` gefunden werden, benachrichtigt die `GetAttribute`-Methode den Benutzer, dass keine Attribute gefunden wurden, und zeigt den Namen der Methode oder Klasse an, die das Attribut nicht enthält. Wenn ein Attribut gefunden wird, werden die Felder `Name`, `Level` und `Reviewed` in der Konsole angezeigt.  
  
 Sie können die Elemente der <xref:System.Type>-Klasse verwenden, um die einzelnen Methoden und Elemente der übergebenen Klasse abzurufen. In diesem Beispiel wird zuerst das **Type**-Objekt abgefragt, um Attributinformationen für die Klassenebene abzurufen. Als Nächstes wird <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> verwendet, um Instanzen aller Methoden in einem Array von <xref:System.Reflection.MemberInfo?displayProperty=nameWithType>-Objekten zu platzieren, um Attributinformationen für die Methodenebene abzurufen. Sie können mithilfe der <xref:System.Type.GetProperties%2A?displayProperty=nameWithType>-Methode nach Attributen auf Eigenschaftenebene oder mithilfe von <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> nach Attributen auf Konstruktorebene suchen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [Attribute](../../../docs/standard/attributes/index.md)
