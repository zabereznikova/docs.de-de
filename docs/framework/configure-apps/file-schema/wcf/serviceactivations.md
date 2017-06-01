---
title: "&lt;serviceActivations&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;serviceActivations&gt;
Ein Konfigurationselement, das Ihnen ermöglicht, Einstellungen zur Definition virtueller Dienstaktivierungseinstellungen hinzuzufügen, die Ihren [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Diensttypen entsprechen.  Auf diese Weise können Sie in WAS\/IIS gehostete Dienste ohne eine SVC\-Datei aktivieren.  
  
## Syntax  
  
```  
  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.|  
  
## Hinweise  
 Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei **web.config** konfiguriert werden.  
  
```  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 Mit dieser Konfiguration können Sie das GreetingService\-Element aktivieren, ohne eine SVC\-Datei zu verwenden.  
  
 Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.  Sie müssen das `web.config`\-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.  Außerdem ist `serviceHostingEnvironment` ein machinetoApplication\-vererbbarer Abschnitt.  Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.  
  
 Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.  Sie erfordert Erweiterungen im relativeAddress\-Element, z. B.  **.svc**, **.xoml** oder **.xamlx**.  Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.  Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC\-Registrierungen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>