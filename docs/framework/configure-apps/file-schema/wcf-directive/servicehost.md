---
title: "@ServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# @ServiceHost
Ordnet die Factory zu, die zum Generieren des Diensthosts mit dem zu hostenden Dienst verwendet wird, sowie andere Programmieraspekte, die für den Zugriff und die Kompilierung des in der SVC\-Datei enthaltenen Hostingcodes erforderlich sind.  
  
## Syntax  
  
```  
  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## Attribute  
  
#### Dienst  
 Der CLR\-Typname des gehosteten Diensts.  Dabei sollte es sich um einen qualifizierten Namen eines Typs handeln, der mindestens einen Dienstkontakt implementiert.  
  
#### Factory  
 Der CLR\-Typname der Diensthostfactory, der zum Instanziieren des Diensthosts verwendet wird.  Dieses Attribut ist optional.  Falls nicht angegeben, wird die Standard\-<xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt.  
  
#### Debuggen  
 Gibt an, ob der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Dienst mit Debugsymbolen kompiliert werden soll.  Lautet `true`, wenn der [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienst mit Debugsymbolen kompiliert werden soll, andernfalls `false`.  
  
#### Sprache  
 Gibt die Sprache zum Kompilieren des gesamten Inlinecodes in der Datei \(SVC\) an.  Die Werte können jede von .NET unterstützte Sprache darstellen, darunter C\#, VB und JS, die sich jeweils auf C\#, Visual Basic .NET und JScript .NET beziehen.  Dieses Attribut ist optional.  
  
#### CodeBehind  
 Gibt die Quelldatei an, die den XML\-Webdienst implementiert, wenn sich die Klasse, die den XML\-Webdienst implementiert, nicht in derselben Datei befindet und nicht in eine Assembly kompiliert oder im Verzeichnis \\Bin gespeichert wurde.  
  
## Hinweise  
 Der <xref:System.ServiceModel.ServiceHost>, der verwendet wird, um den Dienst zu hosten, ist ein Aspekt der Erweiterbarkeit innerhalb des [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Programmiermodells.  Ein Factorymuster wird zum Instanziieren von <xref:System.ServiceModel.ServiceHost> verwendet, da es sich möglicherweise um einen polymorphen Typ handelt, der von der Hostumgebung nicht direkt instanziiert werden sollte.  
  
 Die Standardimplementierung verwendet <xref:System.ServiceModel.Activation.ServiceHostFactory>, um eine Instanz von <xref:System.ServiceModel.ServiceHost> zu erstellen.  Sie können jedoch auch eine eigene Factory bereitstellen \(eine, die den abgeleiteten Host zurückgibt\), indem Sie den CLR\-Typnamen Ihrer Factoryimplementierung in der [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktive angeben.  
  
 Wenn Sie eine eigene benutzerdefinierte Diensthostfactory statt der Standardfactory verwenden möchten, geben Sie einfach wie folgt den Typnamen in der [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktive an:  
  
```  
<% @ServiceHost Factory=”DerivedFactory” Service=”MyService” %>  
```  
  
 Halten Sie die Factoryimplementierungen so einfach wie möglich.  Falls die benutzerdefinierte Logik umfassend ist, kann der Code einfacher wiederverwendet werden, wenn Sie diese Logik im Host und nicht in der Factory platzieren.  
  
 Wenn Sie zum Beispiel einen AJAX\-fähigen Endpunkt für `MyService` aktivieren möchten, legen Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> für den Wert des `Factory`\-Attributs und nicht die Standard\-<xref:System.ServiceModel.Activation.ServiceHostFactory> in der [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\-Direktive fest, wie im folgenden Beispiel dargestellt.  
  
## Beispiel  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## Siehe auch  
 [Benutzerdefinierter Diensthost](../../../../../docs/framework/wcf/samples/custom-service-host.md)