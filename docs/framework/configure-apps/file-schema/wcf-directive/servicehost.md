---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: cb425d9f4dadd97e93946a2b4cd9d059ea8504ce
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051362"
---
# <a name="servicehost"></a>\@ServiceHost

Ordnet die Factory zu, die zum Generieren des Diensthosts mit dem zu hostenden Dienst verwendet wird, sowie andere Programmieraspekte, die für den Zugriff und die Kompilierung des in der SVC-Datei enthaltenen Hostingcodes erforderlich sind.

## <a name="syntax"></a>Syntax

```aspx-csharp
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```

## <a name="attributes"></a>Attribute

### <a name="service"></a>Dienst

Der CLR-Typname des gehosteten Diensts. Dabei sollte es sich um einen qualifizierten Namen eines Typs handeln, der mindestens einen Dienstkontakt implementiert.

### <a name="factory"></a>Factory

Der CLR-Typname der Diensthostfactory, der zum Instanziieren des Diensthosts verwendet wird. Dieses Attribut ist optional. Falls nicht angegeben, wird die Standard-<xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt.

### <a name="debug"></a>Debug

Gibt an, ob der Windows Communication Foundation (WCF)-Dienst mit Debugsymbolen kompiliert werden soll. `true`, wenn der WCF-Dienst mit Debugsymbolen kompiliert werden soll. andernfalls `false` .

### <a name="language"></a>Sprache

Gibt die Sprache zum Kompilieren des gesamten Inlinecodes in der Datei (SVC) an. Die Werte können beliebige darstellen. NET-unterstützte Sprache, einschließlich `C#` , `VB` und `JS` , die auf c#, Visual Basic bzw. JScript .net verweisen. Dieses Attribut ist optional.

### <a name="codebehind"></a>CodeBehind

Gibt die Quelldatei an, die den XML-Webdienst implementiert, wenn sich die Klasse, die den XML-Webdienst implementiert, nicht in derselben Datei befindet und nicht in eine Assembly kompiliert und im Verzeichnis " *\bin* " abgelegt wurde.

## <a name="remarks"></a>Hinweise

Der <xref:System.ServiceModel.ServiceHost> , der zum Hosten des Diensts verwendet wird, ist ein Erweiterbarkeits Punkt innerhalb des Windows Communication Foundation (WCF)-Programmiermodells. Ein Factorymuster wird zum Instanziieren von <xref:System.ServiceModel.ServiceHost> verwendet, da es sich möglicherweise um einen polymorphen Typ handelt, der von der Hostumgebung nicht direkt instanziiert werden sollte.

Die Standardimplementierung verwendet <xref:System.ServiceModel.Activation.ServiceHostFactory>, um eine Instanz von <xref:System.ServiceModel.ServiceHost> zu erstellen. Sie können jedoch eine eigene Factory bereitstellen (eine, die den abgeleiteten Host zurückgibt), indem Sie den CLR-Typnamen Ihrer Factory-Implementierung in der- `@ServiceHost` Direktive angeben.

Wenn Sie anstelle der Standardfactory eine eigene benutzerdefinierte Diensthostfactory verwenden möchten, geben Sie einfach den Typnamen in der- `@ServiceHost` Direktive wie folgt an.

```xml
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>
```

Halten Sie die Factoryimplementierungen so einfach wie möglich. Falls die benutzerdefinierte Logik umfassend ist, kann der Code einfacher wiederverwendet werden, wenn Sie diese Logik im Host und nicht in der Factory platzieren.

Wenn Sie z. b. einen AJAX-aktivierten Endpunkt für aktivieren möchten `MyService` , geben Sie den <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> für den Wert des `Factory` Attributs anstelle des Standardwerts <xref:System.ServiceModel.Activation.ServiceHostFactory> in der- `@ServiceHost` Direktive an, wie im folgenden Beispiel gezeigt:

```aspx-csharp
<% @ServiceHost
Service="MyService"
Language="C#"
Debug="true"
Factory="WebScriptServiceHostFactory"
%>
```

## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierter Diensthost](../../../wcf/samples/custom-service-host.md)
