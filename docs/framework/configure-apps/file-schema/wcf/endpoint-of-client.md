---
title: "&lt;endpoint&gt; von &lt;client&gt; | Microsoft Docs"
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
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# &lt;endpoint&gt; von &lt;client&gt;
Gibt die Vertrags\-, Bindungs\- und Adresseigenschaften für den Kanalendpunkt an, mit dem Clients eine Verbindung zu Dienstendpunkten auf dem Server herstellen.  
  
## Syntax  
  
```  
  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"  
   endpointConfiguration=”String”  
   kind=”String”  
   name="String"  
</endpoint>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Adresse|Erforderliches Zeichenfolgenattribut.<br /><br /> Gibt die Adresse des Endpunkts an.  Der Standardwert ist eine leere Zeichenfolge.  Die Adresse muss ein absoluter URI sein.|  
|behaviorConfiguration|Eine Zeichenfolge mit dem Namen des Verhaltens, das zur Instanziierung des Endpunkts verwendet werden soll.  Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden.  Der Standardwert ist eine leere Zeichenfolge.|  
|Bindung|Erforderliches Zeichenfolgenattribut.<br /><br /> Eine Zeichenfolge, die den Typ der zu verwendenden Bindung angibt.  Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann.  Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.|  
|bindingConfiguration|Dies ist optional.  Eine Zeichenfolge, die den Namen der Bindungskonfiguration enthält, die beim Instanziieren des Endpunkts verwendet werden soll.  Die Bindungskonfiguration muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden.  Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet.  Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten.  Andernfalls wird unter Umständen eine Ausnahme ausgelöst.|  
|Vertrag \(Contract\)|Erforderliches Zeichenfolgenattribut.<br /><br /> Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.  Die Assembly muss den Vertragstyp implementieren.|  
|endpointConfiguration|Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`\-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist.  Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.|  
|kind|Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt.  Der Typ muss im Abschnitt `<extensions>` oder in machine.config registriert werden.  Wenn nichts angegeben wird, wird ein allgemeiner Channelendpunkt erstellt.|  
|Name|Optionales Zeichenfolgeattribut.  Dieses Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.  Sie können für einen angegebenen Vertragstyp mehrere Clients definieren.  Jede Definition muss sich durch einen eindeutigen Konfigurationsnamen unterscheiden.  Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.  Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Das `name`\-Attribut einer Bindung wird zum Definitionsexport durch WSDL verwendet.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Kopfzeilen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Eine Auflistung von Adressheadern.|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<client\>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.|  
  
## Beispiel  
 Dies ist ein Beispiel für eine Kanalendpunkt\-Konfiguration.  
  
```  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>   
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>   
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>   
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>   
 [WCF\-Clientkonfiguration](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clients](../../../../../docs/framework/wcf/feature-details/clients.md)