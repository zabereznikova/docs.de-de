---
title: Windows Communication Foundation-Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: 50c430489144589f6deb0930aeb3006bcb7efe8c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262098"
---
# <a name="windows-communication-foundation-bindings"></a>Windows Communication Foundation-Bindungen

Windows Communication Foundation (WCF) trennt, wie die Software für eine Anwendung von der Kommunikation mit anderer Software verfasst wird. Mit Bindungen werden Transport, Codierung und Protokolldetails angegeben, die für die Kommunikation zwischen Clients und Diensten erforderlich sind. WCF verwendet Bindungen zum Generieren der zugrunde liegenden Netzwerkdarstellung des Endpunkts, sodass die meisten Bindungs Details von den Parteien, die kommunizieren, vereinbart werden müssen. Das geschieht am einfachsten, indem die Clients eines Diensts dieselbe Bindung wie der Endpunkt dieses Diensts verwenden. Weitere Informationen hierzu finden Sie unter [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](../using-bindings-to-configure-services-and-clients.md).  
  
 Eine Bindung besteht aus einer Auflistung von Bindungselementen. Jedes Element beschreibt einige Aspekte der Kommunikation zwischen dem Endpunkt und den Clients. Eine Bindung muss mindestens ein Transportbindungselement, mindestens ein Nachrichten codierendes Bindungselement (was standardmäßig durch das Transportbindungselement erfolgen kann) und eine beliebige Zahl von sonstigen Protokollbindungselementen umfassen. In dem Prozess, der aus dieser Beschreibung eine Laufzeit aufbaut, kann jedes Bindungselement Code zu dieser Laufzeit beitragen.  
  
 WCF bietet Bindungen, die eine allgemeine Auswahl von Bindungs Elementen enthalten. Sie können diese Bindungen mit ihren Standardeinstellungen verwenden oder die Standardwerte den Benutzeranforderungen entsprechend ändern. Diese vom System bereitgestellten Bindungen verfügen über Eigenschaften, die eine direkte Steuerung der Bindungselemente und ihrer Einstellungen zulassen. Durch die Vergabe eines eigenen Namens für jede Version der Bindung können Sie leicht mit mehreren Versionen einer Bindung gleichzeitig arbeiten. Weitere Informationen finden Sie unter [Konfigurieren von System-Provided Bindungen](configuring-system-provided-bindings.md).  
  
 Wenn Sie eine Auflistung mit Bindungselementen benötigen, die in den vom System bereitgestellten Bindungen nicht enthalten ist, können Sie eine benutzerdefinierte Bindung mit einer Auflistung der erforderlichen Bindungselemente erstellen. Diese benutzerdefinierten Bindungen sind einfach zu erstellen und erfordern keine neue Klasse, sie verfügen jedoch über keine Eigenschaften zum Steuern der Bindungselemente oder deren Einstellungen. Sie können auf die Bindungselemente zugreifen und ihre Einstellungen durch die Auflistung ändern, die sie enthält. Weitere Informationen finden Sie unter [benutzerdefinierte Bindungen](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Konfigurieren der vom System bereitgestellten Bindungen](configuring-system-provided-bindings.md)  
 Beschreibt, wie die von WCF bereitgestellten Bindungen verwendet und geändert werden, um gängige Szenarios zu unterstützen.  
  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../using-bindings-to-configure-services-and-clients.md)  
 Beschreibt, wie Windows Communication Foundation (WCF)-Bindungen für Dienste und Clients imperativ im Code und deklarativ mithilfe der Konfiguration definiert werden.  
  
 [Benutzerdefinierte Bindungen](../extending/custom-bindings.md)  
 Beschreibt Zweck und Verwendung einer <xref:System.ServiceModel.Channels.CustomBinding>.  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Erweitern von Bindungen](../extending/extending-bindings.md)
