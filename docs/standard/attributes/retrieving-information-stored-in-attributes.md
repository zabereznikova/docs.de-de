---
title: Abrufen von Informationen aus Attributen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a>Abrufen von Informationen aus Attributen
Das Abrufen eines benutzerdefinierten Attributs ist ein einfacher Vorgang. Deklarieren Sie zuerst eine Instanz des Attributs ein, die Sie abrufen möchten. Verwenden Sie dann die <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> Methode, um das neue Attribut auf den Wert des Attributs initialisieren Sie abrufen möchten. Sobald das neue Attribut initialisiert wurde, verwenden Sie einfach die Eigenschaften zum Abrufen der Werte an.  
  
> [!IMPORTANT]
>  In diesem Thema wird beschrieben, wie zum Abrufen der Attribute für Code, der in den Ausführungskontext geladen wird. Attribute für Code in den ReflectionOnly Kontext geladen abzurufen, verwenden Sie die <xref:System.Reflection.CustomAttributeData> Klasse, entsprechend [wie: Laden von Assemblys in den Reflection-Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 In diesem Abschnitt werden die folgenden Möglichkeiten zum Abrufen von Attribute beschrieben:  
  
-   [Eine einzelne Instanz eines Attributs abrufen](#cpconretrievingsingleinstanceofattribute)  
  
-   [Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Eine einzelne Instanz eines Attributs abrufen  
 Im folgenden Beispiel die `DeveloperAttribute` (im vorherigen Abschnitt beschrieben) wird angewendet, um die `MainApp` Klasse auf Klassenebene. Die `GetAttribute` -Methode verwendet **wurde** zum Abrufen der Werte, die in gespeicherten `DeveloperAttribute` auf Klassenebene, bevor sie auf der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Dieses Programm zeigt folgenden Text bei der Ausführung.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Wenn das Attribut nicht gefunden wird, die **wurde** -Methode initialisiert `MyAttribute` mit einem Nullwert. In diesem Beispiel prüft `MyAttribute` für eine solche Instanz und der Benutzer benachrichtigt, wenn kein Attribut gefunden wird. Wenn die `DeveloperAttribute` befindet sich nicht im Gültigkeitsbereich Klasse die folgende Meldung in der Konsole anzeigt.  
  
```  
The attribute was not found.   
```  
  
 In diesem Beispiel wird davon ausgegangen, dass die Attributdefinition im aktuellen Namespace ist. Denken Sie daran, um den Namespace zu importieren, in dem sich die Attributdefinition befindet, ist er nicht im aktuellen Namespace.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet  
 Im vorherigen Beispiel die Klasse, um zu überprüfen und bestimmte zu suchenden Attributs zu übergeben sind <xref:System.Attribute.GetCustomAttribute%2A>. Dieser Code funktioniert gut, wenn nur eine Instanz eines Attributs auf Klassenebene angewendet wird. Jedoch, wenn mehrere Instanzen eines Attributs auf der Klassenebene des gleichen angewendet werden die **wurde** Methode nicht alle Informationen abgerufen werden. In Fällen, in dem mehrere Instanzen des gleichen Attributs in demselben Gültigkeitsbereich angewendet werden, können Sie <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> alle Instanzen eines Attributs in einem Array platzieren. Angenommen, zwei Instanzen von `DeveloperAttribute` auf Klassenebene derselben Klasse angewendet werden die `GetAttribute` Methode zum Anzeigen der Informationen in beide Attribute geändert werden kann. Beachten Sie, dass mehrere Attribute auf derselben Ebene anzuwenden, muss das Attribut definiert werden, mit der **AllowMultiple** -Eigenschaftensatz auf **"true"** in der <xref:System.AttributeUsageAttribute>.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die **GetCustomAttributes** Methode, um ein Array zu erstellen, die alle Instanzen von verweist `DeveloperAttribute` in einer angegebenen Klasse. Anschließend werden die Werte aller Attribute in der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Wenn keine Attribute gefunden werden, weist dieser Code den Benutzer an. Andernfalls enthält die Informationen in beiden Instanzen des `DeveloperAttribute` wird angezeigt.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet  
 Die <xref:System.Attribute.GetCustomAttributes%2A> und <xref:System.Attribute.GetCustomAttribute%2A> Methoden nicht suchen eine gesamte Objektklasse und alle Instanzen eines Attributs in dieser Klasse zurück. Suchen sie stattdessen nur eine angegebene Methode oder ein Element zu einem Zeitpunkt aus. Wenn Sie eine Klasse mit dem gleichen Attribut auf jedes Element angewendet haben, und zum Abrufen der Werte in den Attributen, die auf diesen Member angewendet werden sollen, Sie müssen angeben jeder Methode oder der Member einzeln an **GetCustomAttributes** und  **Wurde**.  
  
 Im folgenden Codebeispiel wird eine Klasse als Parameter akzeptiert und sucht nach der `DeveloperAttribute` (definierten zuvor) auf Klassenebene und in jeder einzelnen Methode dieser Klasse.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Wenn keine Instanzen von der `DeveloperAttribute` befinden sich auf der Methoden- oder Klassenebene, die `GetAttribute` Methode benachrichtigt den Benutzer, die keine Attribute gefunden wurden, und zeigt den Namen der Methode oder Klasse, die nicht das Attribut enthält. Wenn ein Attribut gefunden wird, die `Name`, `Level`, und `Reviewed` Felder werden in der Konsole angezeigt.  
  
 Können Sie die Mitglieder der <xref:System.Type> Klasse, um die einzelnen Methoden und Elemente in der übergebenen Klasse abrufen. Abfragen in diesem Beispiel wird zuerst die **Typ** Objekt, Informationen über Bildattribute für Klassenebene abgerufen werden. Als Nächstes verwendet <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> Instanzen aller Methoden in ein Array von <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> Objekte zum Abrufen von Informationen über Bildattribute für Methodenebene. Sie können auch die <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> Methode, um die Prüfung der Attribute auf der Eigenschaftenebene oder <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> zu suchende Attribute auf der Konstruktorebene.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [Attribute](../../../docs/standard/attributes/index.md)
