---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704179"
---
# <a name="compositeduplex"></a>\<compositeDuplex>
Definiert das zu verwendende Bindungselement, wenn der Client einen Endpunkt für den Dienst zum Senden von Nachrichten zurück an den Client verfügbar machen muss.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<compositeDuplex>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|clientBaseAddress|Ein URI, der die Adresse des hinteren Kanals im Duplexmodus festlegt. Diese Adresse wird vom Dienst zum Herstellen des Kontakts und dem Aufbau einer Verbindung mit dem Client verwendet.<br /><br /> Wenn dieses Attribut nicht festgelegt ist, wird eine Standardadresse "`full qualified name+default port\TemporaryIndigoAddress\guid`" wird generiert. Die Standardeinstellung ist `null`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&amp;#160;B. HTTP. Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird.   
  
 Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen. Die Clientadresse wird vom `clientBaseAddress`-Attribut bereitgestellt. Beachten Sie, dass Windows Communication Foundation (WCF) automatisch eine ClientBaseAddress generiert, wenn der Benutzer keine explizit festlegt.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
