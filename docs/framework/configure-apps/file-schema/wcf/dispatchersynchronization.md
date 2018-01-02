---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57477ea60337e5032b80bd9ae8da850099dd08f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;

Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.

\<system.serviceModel > \<Verhalten > \<EndpointBehaviors > \<Verhalten >

## <a name="syntax"></a>Syntax

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a>Typ

`Type`

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

| Attribut               | Beschreibung       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Ein boolescher Wert, der angibt, ob das asynchrone Sendeverhalten aktiviert ist. |
| `maxPendingReceives`    | Eine ganze Zahl, die die Anzahl der gleichzeitigen Empfangsvorgänge angibt, die auf dem Kanal ausgegeben werden können.<br /><br /> Konfigurieren Sie diesen Wert erst, nachdem Sie das Einschränkungsverhalten für den Dienst ordnungsgemäß konfiguriert haben. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |  
| ------- | ----------- |  
| [\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an. |

## <a name="see-also"></a>Siehe auch

 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
