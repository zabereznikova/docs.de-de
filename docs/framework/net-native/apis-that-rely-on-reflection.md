---
title: APIs, die auf Refelktion beruhen
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 1d8daceb6b744b984f86b011ad7952d0da583a79
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181094"
---
# <a name="apis-that-rely-on-reflection"></a>APIs, die auf Refelktion beruhen
In einigen Fällen ist die Verwendung von Reflektion im Code nicht offensichtlich, sodass die .net Native-Toolkette keine Metadaten beibehält, die zur Laufzeit benötigt werden. In diesem Thema werden einige gängige APIs oder Programmiermuster behandelt, die nicht als Teil der Reflektions-API betrachtet werden, aber Reflektion benötigen, um erfolgreich ausgeführt zu werden. Wenn Sie diese im Quellcode verwenden, können Sie Informationen darüber in die Laufzeitanweisungsdatei (*.rd.xml) einfügen, sodass Aufrufe dieser APIs zur Laufzeit keine [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme oder sonstige Ausnahmen auslösen.  
  
## <a name="typemakegenerictype-method"></a>Type.MakeGenericType-Methode  
 Sie können einen generischen Typ `AppClass<T>` dynamisch instanziieren, indem Sie die <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode aufrufen. Dazu verwenden Sie Code wie den folgenden:  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 Damit dieser Code zur Laufzeit erfolgreich ist, sind mehrere Elemente von Metadaten erforderlich. Das erste sind `Browse`-Metadaten für den nicht instanziierten generischen Typ `AppClass<T>`:  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 Auf diese Weise kann der Aufruf der <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode erfolgreich sein und ein gültiges <xref:System.Type>-Objekt zurückgeben.  
  
 Aber auch wenn Sie Metadaten für den nicht instanziierten generischen Typ hinzufügen, löst der Aufruf der <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode eine [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme aus:  
  
Dieser Vorgang kann nicht ausgeführt werden, weil Metadaten für den folgenden Typ aus Leistungsgründen entfernt wurden:  
  
`App1.AppClass`1<System. Int32>'.  
  
 Sie können der Laufzeitdirektivendatei die folgende Laufzeitdirektive hinzufügen, um `Activate`-Metadaten für die spezifische Instanziierung über `AppClass<T>` von <xref:System.Int32?displayProperty=nameWithType> hinzuzufügen:  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 Jede andere Instanziierung über `AppClass<T>` erfordert eine separate Anweisung, wenn sie mit der <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode erstellt und nicht statisch verwendet wird.  
  
## <a name="methodinfomakegenericmethod-method"></a>MethodInfo.MakeGenericMethod-Methode  
 In einer Klasse `Class1` mit einer generischen Methode `GetMethod<T>(T t)` kann `GetMethod` durch Reflektion mithilfe von Code wie dem folgenden aufgerufen werden:  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 Damit dieser Code erfolgreich ausgeführt wird, sind mehrere Elemente von Metadaten erforderlich:  
  
- `Browse`-Metadaten für den Typ, dessen Methode Sie aufrufen möchten.  
  
- `Browse`-Metadaten für die Methode, die Sie aufrufen möchten.  Ist es eine öffentliche Methode, umfasst das Hinzufügen von öffentlichen `Browse`-Metadaten für den enthaltenden Typ auch die Methode.  
  
- Dynamische Metadaten für die Methode, die Sie aufrufen möchten, damit der Reflektionsaufruf-Delegat nicht von der .net Native-Toolkette entfernt wird. Wenn dynamische Metadaten für die Methode fehlen, wird beim Aufruf der <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>-Methode die folgende Ausnahme ausgelöst:  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 Die folgenden Laufzeitanweisungen stellen sicher, dass alle erforderlichen Metadaten verfügbar sind:  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 Für jede unterschiedliche Instanziierung der Methode, die dynamisch aufgerufen wird, ist eine `MethodInstantiation`-Direktive erforderlich, und das `Arguments`-Element wird jedem unterschiedlichen Instanziierungsargument entsprechend aktualisiert.  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a>Methoden Array.CreateInstance und Type.MakeTypeArray  
 Das folgende Beispiel ruft die Methoden <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> und <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> für einen Typ `Class1` auf.  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 Wenn keine Array-Metadaten vorhanden sind, führt dies zu folgender Fehlermeldung:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 `Browse`-Metadaten für den Arraytyp sind erforderlich, um ihn dynamisch zu instanziieren.  Die folgende Laufzeitdirektive ermöglicht die dynamische Instanziierung von `Class1[]`.  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](getting-started-with-net-native.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
