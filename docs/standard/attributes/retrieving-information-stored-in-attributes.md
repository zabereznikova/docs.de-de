---
title: "Abrufen von Informationen aus Attributen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Attribute [.NET Framework], Abrufen"
  - "Mehrere Attributinstanzen"
  - "Abrufen von Attributen"
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Abrufen von Informationen aus Attributen
Das Abrufen eines benutzerdefinierten Attributs ist ein unkomplizierter Vorgang.  Deklarieren Sie zunächst eine Instanz des Attributs, das abgerufen werden soll.  Initialisieren Sie dann das neue Attribut mithilfe der <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>\-Methode mit dem Wert des abzurufenden Attributs.  Nach der Initialisierung des neuen Attributs können Sie die Werte dann einfach über die Eigenschaften abrufen.  
  
> [!IMPORTANT]
>  In diesem Thema wird das Abrufen von Attributen für Code beschrieben, der in den Ausführungskontext geladen wurde.  Um Attribute für Code abzurufen, der in den reflektionsbezogenen Kontext geladen wurde, verwenden Sie die <xref:System.Reflection.CustomAttributeData>\-Klasse, wie unter [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) beschrieben.  
  
 In diesem Abschnitt werden die folgenden Möglichkeiten zum Abrufen von Attributen beschrieben:  
  
-   [Abrufen einer einzigen Instanz eines Attributs](#cpconretrievingsingleinstanceofattribute)  
  
-   [Abrufen mehrerer, auf denselben Gültigkeitsbereich angewendeter Instanzen eines Attributs](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Abrufen mehrerer, auf verschiedene Gültigkeitsbereiche angewendeter Instanzen eines Attributs](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## Abrufen einer einzigen Instanz eines Attributs  
 Im folgenden Beispiel wird `DeveloperAttribute`, das im vorherigen Abschnitt beschrieben wurde, auf Klassenebene auf die `MainApp`\-Klasse angewendet.  Die `GetAttribute`\-Methode verwendet **GetCustomAttribute**, um die in `DeveloperAttribute` auf Klassenebene gespeicherten Werte abzurufen, bevor sie auf der Konsole angezeigt werden.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Das Programm zeigt bei der Ausführung den folgenden Text an.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Wenn das Attribut nicht gefunden wird, initialisiert die **GetCustomAttribute**\-Methode `MyAttribute` mit einem NULL\-Wert.  In diesem Beispiel wird `MyAttribute` auf eine solche Instanz überprüft. Wenn kein Attribut gefunden wird, wird der Benutzer benachrichtigt.  Wenn `DeveloperAttribute` im Gültigkeitsbereich der Klasse nicht gefunden werden kann, wird die folgende Meldung in der Konsole angezeigt.  
  
```  
The attribute was not found.   
```  
  
 In diesem Beispiel wird vorausgesetzt, dass sich die Attributdefinition im aktuellen Namespace befindet.  Daher müssen Sie den Namespace, in dem sich die Attributdefinition befindet, unbedingt importieren, sofern es sich nicht um den aktuellen Namespace handelt.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## Abrufen mehrerer, auf denselben Gültigkeitsbereich angewendeter Instanzen eines Attributs  
 Im vorherigen Beispiel wurden die zu prüfende Klasse und das angegebene Attribut, das gesucht werden soll, an <xref:System.Attribute.GetCustomAttribute%2A> übergeben.  Dieser Code funktioniert dann problemlos, wenn nur eine Instanz eines Attributs auf Klassenebene angewendet wird.  Wenn jedoch mehrere Instanzen eines Attributs auf derselben Klassenebene angewendet werden, ruft die **GetCustomAttribute**\-Methode nicht alle Informationen ab.  Wenn mehrere Instanzen des gleichen Attributs in demselben Gültigkeitsbereich angewendet werden, können Sie mit <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName> alle Instanzen eines Attributs in einem Array platzieren.  Wenn z. B. zwei Instanzen von `DeveloperAttribute` auf Klassenebene derselben Klasse angewendet werden, können Sie die `GetAttribute`\-Methode dahingehend ändern, dass sie die in beiden Attributen gefundenen Informationen anzeigt.  Wenn Sie mehrere Attribute auf derselben Ebene anwenden möchten, müssen Sie die **AllowMultiple**\-Eigenschaft im <xref:System.AttributeUsageAttribute> auf **true** festlegen.  
  
 Das folgende Codebeispiel veranschaulicht, wie Sie mit der **GetCustomAttributes**\-Methode ein Array erstellen, das auf sämtliche Instanzen von `DeveloperAttribute`in allen angegebenen Klassen verweist.  Die Werte aller Attribute werden anschließend in der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Wenn keine Attribute gefunden werden, gibt der Code eine Warnung an den Benutzer aus.  Andernfalls werden die in beiden Instanzen von `DeveloperAttribute` enthaltenen Informationen angezeigt.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## Abrufen mehrerer, auf verschiedene Gültigkeitsbereiche angewendeter Instanzen eines Attributs  
 Die <xref:System.Attribute.GetCustomAttributes%2A>\-Methode und die <xref:System.Attribute.GetCustomAttribute%2A>\-Methode suchen nicht in der gesamten Klasse und geben nicht alle Instanzen eines Attributs in der Klasse zurück.  Sie suchen jeweils nur in einer angegebenen Methode oder Eigenschaft.  Angenommen, Sie verfügen über eine Klasse, in der auf alle Member dasselbe Attribut angewendet wurde. Um die Werte aller Attribute, die auf diese Member angewendet wurden, abzurufen, müssen Sie alle Methoden bzw. Member in **GetCustomAttributes** und **GetCustomAttribute** jeweils einzeln angeben.  
  
 Im folgenden Codebeispiel wird eine Klasse als Parameter verwendet und auf Klassenebene und in jeder einzelnen Methode der Klasse nach dem zuvor definierten `DeveloperAttribute`  gesucht.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Wenn auf Methoden\- oder Klassenebene keine Instanzen von `DeveloperAttribute` gefunden werden, benachrichtigt die `GetAttribute`\-Methode den Benutzer, dass keine Attribute gefunden wurden, und zeigt den Namen der Methode bzw. Klasse an, die das Attribut nicht enthält.  Wenn ein Attribut gefunden wird, werden das `Name`\-Feld, das `Level`\-Feld und das `Reviewed`\-Feld in der Konsole angezeigt.  
  
 Mit den Membern der <xref:System.Type>\-Klasse können Sie die einzelnen Methoden und Member in der übergebenen Klasse abrufen.  In diesem Beispiel wird zuerst das **Type**\-Objekt abgefragt, um Attributinformationen für die Klassenebene abzurufen.  Anschließend werden mit <xref:System.Type.GetMethods%2A?displayProperty=fullName> Instanzen aller Methoden in einem Array von <xref:System.Reflection.MemberInfo?displayProperty=fullName>\-Objekten platziert, um Attributinformationen für die Methodenebene abzurufen.  Außerdem können Sie mithilfe der <xref:System.Type.GetProperties%2A?displayProperty=fullName>\-Methode auf Eigenschaftenebene und mithilfe der <xref:System.Type.GetConstructors%2A?displayProperty=fullName>\-Methode auf Konstruktorebene nach Attributen suchen.  
  
## Siehe auch  
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Attribute](../../../docs/standard/attributes/index.md)