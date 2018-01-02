---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1aeb100e1b8e160d30566cd43d67cbf49c6b5c4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsoapprocessinggt"></a>&lt;soapProcessing&gt;

Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.

**\<System. ServiceModel >**   
&nbsp;&nbsp;**\<Verhalten >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<EndpointBehaviors >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Verhalten >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<SoapProcessing >**

## <a name="syntax"></a>Syntax

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|                   | Beschreibung |
| ----------------- | ----------- |
| `processMessages` | Ein boolescher Wert, der angibt, ob Nachrichten zwischen SOAP-Nachrichtenversionen gemarshallt werden sollen. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keiner

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Verhalten >**](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | Gibt ein Endpunktverhalten an. |

## <a name="remarks"></a>Hinweise

SOAP-Verarbeitung ist der Prozess, bei dem Nachrichten zwischen Nachrichtenversionen konvertiert werden.

Der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Routingdienst kann Nachrichten von einem Protokoll in ein anderes konvertieren. Wenn die Versionen eingehender und ausgehender Nachrichten unterschiedlich sind, wird eine neue Nachricht mit der richtigen Version erstellt. Verarbeiten von Nachrichten von einem <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` in eine andere erreicht, indem Sie eine neue [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Nachricht, die den Textteil und relevante Header der eingehenden enthält [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Nachricht. Header, die adressierungsspezifisch sind oder auf Routerebene verstanden werden, werden während der Erstellung der neuen WCF-Nachricht nicht verwendet, da diese Header entweder eine andere Version haben (im Fall von Adressierungsheadern) oder als Teil der Kommunikation zwischen dem Client und dem Router verarbeitet wurden.

Ob ein Header in der ausgehenden Nachricht eingefügt wird, wird dadurch bestimmt, ob er als verstanden markiert wurde, als er die eingehende Channelebene durchlief. Nicht akzeptierte Header (z. B. benutzerdefinierte Header) werden nicht entfernt und durchlaufen den Routingdienst, indem sie in die ausgehende Nachricht kopiert werden. Der Nachrichtentext wird in die ausgehende Nachricht kopiert. Die Nachricht wird dann über den Kanal für ausgehende Nachrichten gesendet. Zu diesem Zeitpunkt werden alle relevanten Header und anderen für das Kommunikationsprotokoll/den Transport relevanten Umschlagdaten erstellt und hinzugefügt.

Diese Verarbeitungsschritte erfolgen, wenn das SOAP-Verarbeitungsverhalten angegeben ist. Dies [ \<SoapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) Verhalten ist ein Endpunktverhalten, die auf allen (ausgehend) Clientendpunkten angewendet wird, wenn der Routingdienst startet. in der Standardeinstellung die [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten erstellt und fügt ein neues [ \<SoapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) Verhalten bei `processMessages` festgelegt `true` für jede Clientendpunkt. Wenn Sie ein Protokoll haben, das vom Routingdienst nicht akzeptiert wird, oder das Standardverarbeitungsverhalten überschreiben möchten, können Sie die SOAP-Verarbeitung entweder für den gesamten Routingdienst oder für bestimmte Endpunkte deaktivieren.  Wenn um SOAP-Verarbeitung für den gesamten Routingdienst auf alle Endpunkte zu deaktivieren, legen Sie die `soapProcessing` Attribut des der [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten `false`. Um die SOAP-Verarbeitung für einen bestimmten Endpunkt zu deaktivieren, verwenden Sie dieses Verhalten und legen Sie das `processMessages`-Attribut dieses Verhaltens auf `false` fest. Fügen Sie das Verhalten dann an den Endpunkt an, für den Sie den Standardverarbeitungscode deaktivieren möchten.  Wenn die [ \<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) Verhalten richtet den Routingdienst, überspringt das Endpunktverhalten neu, da bereits eine vorhanden ist.
