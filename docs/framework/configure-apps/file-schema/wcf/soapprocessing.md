---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399542"
---
# \<soapProcessing>

Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a>Syntax  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
  
In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|                   | BESCHREIBUNG |
| ----------------- | ----------- |
| `processMessages` | Ein boolescher Wert, der angibt, ob Nachrichten zwischen SOAP-Nachrichtenversionen gemarshallt werden sollen. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | Gibt ein Endpunktverhalten an. |

## <a name="remarks"></a>Bemerkungen

SOAP-Verarbeitung ist der Prozess, bei dem Nachrichten zwischen Nachrichtenversionen konvertiert werden.

Der Windows Communication Foundation (WCF)-Routing Dienst kann Nachrichten von einem Protokoll in ein anderes Protokoll konvertieren. Wenn die Versionen eingehender und ausgehender Nachrichten unterschiedlich sind, wird eine neue Nachricht mit der richtigen Version erstellt. Meldungen werden von einer <xref:System.ServiceModel.Channels.MessageVersion> zu einer anderen verarbeitet, indem eine neue WCF-Meldung erstellt wird, die den Textteil und relevante Header von der eingehenden WCF-Meldung enthält. Header, die adressierungsspezifisch sind oder auf Routerebene verstanden werden, werden während der Erstellung der neuen WCF-Nachricht nicht verwendet, da diese Header entweder eine andere Version haben (im Fall von Adressierungsheadern) oder als Teil der Kommunikation zwischen dem Client und dem Router verarbeitet wurden.

Ob ein Header in der ausgehenden Nachricht eingefügt wird, wird dadurch bestimmt, ob er als verstanden markiert wurde, als er die eingehende Channelebene durchlief. Nicht akzeptierte Header (z. B. benutzerdefinierte Header) werden nicht entfernt und durchlaufen den Routingdienst, indem sie in die ausgehende Nachricht kopiert werden. Der Nachrichtentext wird in die ausgehende Nachricht kopiert. Die Nachricht wird dann über den Kanal für ausgehende Nachrichten gesendet. Zu diesem Zeitpunkt werden alle relevanten Header und anderen für das Kommunikationsprotokoll/den Transport relevanten Umschlagdaten erstellt und hinzugefügt.

Diese Verarbeitungsschritte erfolgen, wenn das SOAP-Verarbeitungsverhalten angegeben ist. Dieses [\<soapProcessingExtension>](soapprocessing.md) Verhalten ist ein Endpunkt Verhalten, das auf alle Client Endpunkte (ausgehend) angewendet wird, wenn der Routing Dienst gestartet wird. Standardmäßig wird das [\<routing>](routing-of-servicebehavior.md) Verhalten erstellt und ein neues Verhalten angefügt, [\<soapProcessingExtension>](soapprocessing.md) wobei `processMessages` `true` für jeden Client Endpunkt auf festgelegt ist. Wenn Sie ein Protokoll haben, das vom Routingdienst nicht akzeptiert wird, oder das Standardverarbeitungsverhalten überschreiben möchten, können Sie die SOAP-Verarbeitung entweder für den gesamten Routingdienst oder für bestimmte Endpunkte deaktivieren.  Um die SOAP-Verarbeitung für den gesamten Routing Dienst auf allen Endpunkten zu deaktivieren, legen Sie das- `soapProcessing` Attribut des-Verhaltens auf fest [\<routing>](routing-of-servicebehavior.md) `false` . Um die SOAP-Verarbeitung für einen bestimmten Endpunkt zu deaktivieren, verwenden Sie dieses Verhalten und legen Sie das `processMessages`-Attribut dieses Verhaltens auf `false` fest. Fügen Sie das Verhalten dann an den Endpunkt an, für den Sie den Standardverarbeitungscode deaktivieren möchten.  Wenn das [\<routing>](routing-of-servicebehavior.md) Verhalten den Routing Dienst festlegt, wird das erneute Anwenden des Endpunkt Verhaltens übersprungen, da bereits eine vorhanden ist.
