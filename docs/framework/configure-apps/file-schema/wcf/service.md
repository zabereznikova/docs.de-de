---
title: "&lt;service&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# &lt;service&gt;
Das `service`\-Element enthält die Einstellungen für einen Windows Communication Foundation \(WCF\)\-Dienst.  Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.  
  
## Syntax  
  
```  
  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|behaviorConfiguration|Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll.  Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.  Der Standardwert ist eine leere Zeichenfolge.|  
|Name|Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt.  Diese Einstellung muss einem gültigen Typ entsprechen.  Das Format muss `Namespace.Class.` lauten.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Endpunkt \(endpoint\)\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Eine Auflistung von `endpoint`\-Elementen, die diesen Dienst verfügbar machen.|  
|[\<Host\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Gibt den Host dieser Dienstinstanz an.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Dienste\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Das Stammelement aller WCF\-Konfigurationselemente.|  
  
## Hinweise  
 Dienste werden im `services`\-Abschnitt der Konfigurationsdatei definiert.  Eine Assembly kann eine beliebige Anzahl von Diensten enthalten.  Jeder Dienst hat seinen eigenen `service`\-Konfigurationsabschnitt.  Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.  
  
 Das `behaviorConfiguration`\-Element ist optional.  Es identifiziert das vom Dienst verwendete Verhalten.  Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.  
  
 Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt.  Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.  Bindungen sind durch die Kombination aus `name`\-Attribut und `bindingConfiguration`\-Attribut mit Endpunkten verknüpft.  Das `name`\-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist.  Das `bindingConfiguration`\-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird.  Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.  
  
## Beispiel  
 Dies ist ein Beispiel für eine Dienstkonfiguration.  
  
```  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceElement>   
 [Konfigurieren von Diensten](../../../../../docs/framework/wcf/configuring-services.md)