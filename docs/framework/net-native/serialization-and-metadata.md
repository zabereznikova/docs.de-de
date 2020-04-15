---
title: Serialisierung und Metadaten
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: cc9adf0e6627ef3190e74fea5d4f0f3afd581811
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389221"
---
# <a name="serialization-and-metadata"></a>Serialisierung und Metadaten

Wenn Ihre Anwendung Objekte serialisiert und deserialisiert, müssen Sie möglicherweise Einträge zur Laufzeitanweisungsdatei (.rd.xml) hinzufügen, um sicherzustellen, dass die erforderlichen Metadaten zur Laufzeit vorhanden sind. Es gibt zwei Kategorien von Serialisierungsprogrammen, und jedes erfordert eine andere Behandlung in der Laufzeitdirektivendatei:  
  
- Reflektionsbasierte Drittanbieter-Serialisierungsprogramme. Diese erfordern Änderungen an der Laufzeitdirektivendatei und werden im nächsten Abschnitt erläutert.  
  
- Nicht reflektionsbasierte Serialisierungsdateien, die in der .NET Framework-Klassenbibliothek gefunden wurden. Diese erfordern möglicherweise Änderungen an der Laufzeitanweisungsdatei und werden im Abschnitt [Microsoft-Serialisierungsprogramme](#Microsoft) erläutert.  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a>Drittanbieter-Serialisierungsprogramme

 Drittanbieter-Serialisierungsprogramme, einschließlich Newtonsoft.JSON, sind in der Regel reflektionsbasiert. Bei einem BLOB aus serialisierten Daten werden die Felder in den Daten einem konkreten Typ durch Suchen der Felder des Zieltyps nach dem Namen zugewiesen. Durch das Verwenden dieser Bibliotheken werden mindestens [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahmen für alle <xref:System.Type>-Objekte verursacht, die Sie in einer `List<Type>`-Auflistung serialisieren oder deserialisieren möchten.  
  
 Durch fehlende Metadaten für diese Serialisierungsprogramme verursachte Probleme können am einfachsten gelöst werden, indem Sie Typen auflisten, die bei der Serialisierung unter einem einzigen Namespace verwendet werden (z. B. `App.Models`) und eine `Serialize`-Metadatenanweisung darauf anwenden:  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Informationen zur im Beispiel verwendeten Syntax finden Sie unter [ \<Namespace> Element](namespace-element-net-native.md).  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a>Microsoft-Serialisierungsprogramme

 Obwohl die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und <xref:System.Xml.Serialization.XmlSerializer> nicht auf Reflektion angewiesen sind, muss dennoch Code basierend auf dem Objekt, das serialisiert oder deserialisiert werden soll, generiert werden. Die überladenen Konstruktoren für die einzelnen Serialisierungsprogramme enthalten einen <xref:System.Type> -Parameter, der angibt, welcher Typ serialisiert oder deserialisiert werden soll. Wie Sie diesen Typ im Code angeben, definiert die Aktion, die Sie ausführen müssen, wie in den nächsten beiden Abschnitten erläutert wird.  
  
### <a name="typeof-used-in-the-constructor"></a>Im Konstruktor verwendetes "typeof"-Schlüsselwort

 Wenn Sie einen Konstruktor dieser Serialisierungsklassen [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) aufrufen und den Operator "C"-Typof in den Methodenaufruf einbeziehen, **müssen Sie keine zusätzliche Arbeit erledigen.** In jedem der folgenden Aufrufe eines Serialisierungsklassenkonstruktors wird z. B. das `typeof`-Schlüsselwort als Teil des Ausdrucks verwendet, der an den Konstruktor übergeben wird.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Der .NET Native-Compiler verarbeitet diesen Code automatisch.  
  
### <a name="typeof-used-outside-the-constructor"></a>Außerhalb des Konstruktors verwendetes "typeof"-Schlüsselwort

 Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und den [Operator](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) "C" außerhalb des Ausdrucks verwenden, der dem Parameter des Konstruktors <xref:System.Type> bereitgestellt wird, wie im folgenden Code, kann der .NET Native-Compiler den Typ nicht auflösen:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 In diesem Fall müssen Sie den Typ in der Laufzeitanweisungsdatei angeben, indem Sie einen Eintrag wie den folgenden hinzufügen:  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Wenn Sie einen Konstruktor wie <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> z. B. <xref:System.Type> aufrufen und ein Array zusätzlicher Objekte zum Serialisieren bereitstellen, wie im folgenden Code, kann der .NET Native-Compiler diese Typen nicht auflösen.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
Fügen Sie der Laufzeitdirektivendatei Einträge wie die folgenden für jeden Typ hinzu:  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
Informationen zur im Beispiel verwendeten Syntax [ \<](type-element-net-native.md)finden Sie unter Typ> Element .  
  
## <a name="see-also"></a>Weitere Informationen

- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
- [\<Typ> Element](type-element-net-native.md)
- [\<Namespace> Element](namespace-element-net-native.md)
