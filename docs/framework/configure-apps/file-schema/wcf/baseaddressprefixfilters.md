---
title: "&lt;baseAddressPrefixFilters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;baseAddressPrefixFilters&gt;
Stellt eine Auflistung der Konfigurationselemente dar, die Durchlauffilter mit einem Mechanismus zur Auswahl entsprechender IIS\-Bindungen verwenden, wenn die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Anwendung in IIS gehostet wird.  
  
> [!WARNING]
>  \<baseAddressPrefixFilters\> erkennt nicht "localhost". Verwenden Sie stattdessen den vollqualifizierten Computernamen.  
  
## Syntax  
  
```  
  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|Fügt ein Konfigurationselement hinzu, das einen Präfixfilter für die vom Diensthost verwendeten Basisadressen angibt.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.|  
  
## Hinweise  
 Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.  Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.  
  
 IIS\-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.  Auf die Anwendung auf einer Website kann über eine oder mehrere IIS\-Bindungen zugegriffen werden.  IIS\-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.  Das Bindungsprotokoll \(z.&\#160;B. HTTP\) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen \(z.&\#160;B. IP\-Address, Anschluss, Hostheader\) enthalten Daten, die für den Zugriff auf die Website verwendet werden.  
  
 IIS unterstützt die Angabe mehrerer IIS\-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.  Da ein unter einer Website gehosteter [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienst nur die Bindung an eine Basisadresse für jedes Schema ermöglicht, können Sie mithilfe des Präfixfilters die erforderliche Basisadresse des gehosteten Dienstes auswählen.  Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.  
  
 Ihre Website kann beispielsweise die folgenden Basisadressen enthalten.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain\-Ebene anzugeben.  
  
```  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix=”net.tcp://test1.fabrikam.com:8000”/>  
        <add prefix=”http://test2.fabrikam.com:9000”/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.  
  
 Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.  Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.  
  
> [!NOTE]
>  Der Filter unterstützt keine Platzhalter.  Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`\-Liste vorhandene Schemata gebunden sind.  Diese Adressen werden nicht herausgefiltert.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>   
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)