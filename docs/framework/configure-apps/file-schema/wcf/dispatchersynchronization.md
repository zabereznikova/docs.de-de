---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555387"
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;
  
Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.  
  
\<system.serviceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
  
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
| [\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an. |

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
