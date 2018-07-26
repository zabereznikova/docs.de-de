---
title: Windows Communication Foundation-Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: edbcba1cda914d58dee7a11fcb3309254a52a66c
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198142"
---
# <a name="windows-communication-foundation-bindings"></a>Windows Communication Foundation-Bindungen
Windows Communication Foundation (WCF) trennt, wie die Software für eine Anwendung geschrieben wird und wie sie mit anderer Software kommuniziert. Mit Bindungen werden Transport, Codierung und Protokolldetails angegeben, die für die Kommunikation zwischen Clients und Diensten erforderlich sind. WCF verwendet Bindungen, um die zugrunde liegende übertragungsdarstellung des Endpunkts, zu generieren, damit die meisten Details zur Bindung von den codeeigentümern erteilt vereinbart werden müssen, mit die kommuniziert werden. Das geschieht am einfachsten, indem die Clients eines Diensts dieselbe Bindung wie der Endpunkt dieses Diensts verwenden. Weitere Informationen hierzu finden Sie unter [Verwendung von Bindungen zum Konfigurieren von Windows Communication Foundation-Dienste und Clients](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).  
  
 Eine Bindung besteht aus einer Auflistung von Bindungselementen. Jedes Element beschreibt einige Aspekte der Kommunikation zwischen dem Endpunkt und den Clients. Eine Bindung muss mindestens ein Transportbindungselement, mindestens ein Nachrichten codierendes Bindungselement (was standardmäßig durch das Transportbindungselement erfolgen kann) und eine beliebige Zahl von sonstigen Protokollbindungselementen umfassen. In dem Prozess, der aus dieser Beschreibung eine Laufzeit aufbaut, kann jedes Bindungselement Code zu dieser Laufzeit beitragen.  
  
 WCF bietet Bindungen, die allgemeinen Optionen von Bindungselementen enthält. Sie können diese Bindungen mit ihren Standardeinstellungen verwenden oder die Standardwerte den Benutzeranforderungen entsprechend ändern. Diese vom System bereitgestellten Bindungen verfügen über Eigenschaften, die eine direkte Steuerung der Bindungselemente und ihrer Einstellungen zulassen. Durch die Vergabe eines eigenen Namens für jede Version der Bindung können Sie leicht mit mehreren Versionen einer Bindung gleichzeitig arbeiten. Weitere Informationen finden Sie unter [Configuring System-Provided Bindungen](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).  
  
 Wenn Sie eine Auflistung mit Bindungselementen benötigen, die in den vom System bereitgestellten Bindungen nicht enthalten ist, können Sie eine benutzerdefinierte Bindung mit einer Auflistung der erforderlichen Bindungselemente erstellen. Diese benutzerdefinierten Bindungen sind einfach zu erstellen und erfordern keine neue Klasse, sie verfügen jedoch über keine Eigenschaften zum Steuern der Bindungselemente oder deren Einstellungen. Sie können auf die Bindungselemente zugreifen und ihre Einstellungen durch die Auflistung ändern, die sie enthält. Weitere Informationen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 Beschreibt das verwenden und ändern Sie die Bindungen, die WCF zur Unterstützung allgemeiner Szenarien bereitstellt.  
  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 Beschreibt, wie Windows Communication Foundation (WCF)-Bindungen für Dienste und Clients imperativ in Code und deklarativ bei der Konfiguration definieren.  
  
 [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 Beschreibt Zweck und Verwendung einer <xref:System.ServiceModel.Channels.CustomBinding>.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)
