---
title: Serialisierung und Metadaten
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e4db59da7a17e47b8e3df939ec64f5124e04454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-and-metadata"></a>Serialisierung und Metadaten
Wenn Ihre Anwendung Objekte serialisiert und deserialisiert, müssen Sie möglicherweise Einträge zur Laufzeitanweisungsdatei (.rd.xml) hinzufügen, um sicherzustellen, dass die erforderlichen Metadaten zur Laufzeit vorhanden sind. Es gibt zwei Kategorien von Serialisierungsprogrammen, und jedes erfordert eine andere Behandlung in der Laufzeitdirektivendatei:  
  
-   Reflektionsbasierte Drittanbieter-Serialisierungsprogramme. Diese erfordern Änderungen an der Laufzeitdirektivendatei und werden im nächsten Abschnitt erläutert.  
  
-   Nicht-reflektionsbasierte Serialisierungsprogramme aus der. NET Framework-Klassenbibliothek. Diese erfordern möglicherweise Änderungen an der Laufzeitanweisungsdatei und werden im Abschnitt [Microsoft-Serialisierungsprogramme](#Microsoft) erläutert.  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a>Drittanbieter-Serialisierungsprogramme  
 Drittanbieter-Serialisierungsprogramme, einschließlich Newtonsoft.JSON, sind in der Regel reflektionsbasiert. Bei einem BLOB aus serialisierten Daten werden die Felder in den Daten einem konkreten Typ durch Suchen der Felder des Zieltyps nach dem Namen zugewiesen. Durch das Verwenden dieser Bibliotheken werden mindestens [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-Ausnahmen für alle <xref:System.Type>-Objekte verursacht, die Sie in einer `List<Type>`-Auflistung serialisieren oder deserialisieren möchten.  
  
 Durch fehlende Metadaten für diese Serialisierungsprogramme verursachte Probleme können am einfachsten gelöst werden, indem Sie Typen auflisten, die bei der Serialisierung unter einem einzigen Namespace verwendet werden (z. B. `App.Models`) und eine `Serialize`-Metadatenrichtlinie darauf anwenden:  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Informationen zur im Beispiel verwendeten Syntax finden Sie unter [\<Namespace>-Element](../../../docs/framework/net-native/namespace-element-net-native.md).  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a>Microsoft-Serialisierungsprogramme  
 Obwohl die Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und <xref:System.Xml.Serialization.XmlSerializer> nicht auf Reflektion angewiesen sind, muss dennoch Code basierend auf dem Objekt, das serialisiert oder deserialisiert werden soll, generiert werden. Die überladenen Konstruktoren für die einzelnen Serialisierungsprogramme enthalten einen <xref:System.Type> -Parameter, der angibt, welcher Typ serialisiert oder deserialisiert werden soll. Wie Sie diesen Typ im Code angeben, definiert die Aktion, die Sie ausführen müssen, wie in den nächsten beiden Abschnitten erläutert wird.  
  
### <a name="typeof-used-in-the-constructor"></a>Im Konstruktor verwendetes "typeof"-Schlüsselwort  
 Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und das C#-[typeof](~/docs/csharp/language-reference/keywords/typeof.md)-Schlüsselwort in den Methodenaufruf einschließen, **sind keine weiteren Schritte erforderlich**. In jedem der folgenden Aufrufe eines Serialisierungsklassenkonstruktors wird z. B. das `typeof`-Schlüsselwort als Teil des Ausdrucks verwendet, der an den Konstruktor übergeben wird.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler verarbeitet diesen Code automatisch.  
  
### <a name="typeof-used-outside-the-constructor"></a>Außerhalb des Konstruktors verwendetes "typeof"-Schlüsselwort  
 Wenn Sie einen Konstruktor dieser Serialisierungsklassen aufrufen und das C#-[typeof](~/docs/csharp/language-reference/keywords/typeof.md)-Schlüsselwort außerhalb des Ausdrucks verwenden, der für den <xref:System.Type>-Parameter des Konstruktors wie im folgenden Code bereitgestellt wird, kann der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler den Typ nicht auflösen:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 In diesem Fall müssen Sie den Typ in der Laufzeitanweisungsdatei angeben, indem Sie einen Eintrag wie den folgenden hinzufügen:  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Wenn Sie einen Konstruktor wie z. B. <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> aufrufen und ein Array mit zusätzlichen <xref:System.Type>-Objekten zum Serialisieren wie im folgenden Code bereitstellen, kann der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Compiler diese Typen nicht auflösen.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 Sie müssen der Laufzeitanweisungsdatei Einträge wie folgenden für jeden Typ hinzufügen:  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 Informationen zur im Beispiel verwendeten Syntax finden Sie unter [\<Type>-Element](../../../docs/framework/net-native/type-element-net-native.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [\<Type >-Element](../../../docs/framework/net-native/type-element-net-native.md)  
 [\<Namespace>-Element](../../../docs/framework/net-native/namespace-element-net-native.md)
