---
title: "Übersicht über die Integration von COM-Anwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ae704ad9542c162b1c37f3eb9edf31f864cd42e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="integrating-with-com-applications-overview"></a>Übersicht über die Integration von COM-Anwendungen
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet dem Entwickler von verwaltetem Code eine reichhaltige Umgebung zum Erstellen von verbundenen Anwendungen. Wenn Sie jedoch eine erhebliche Investition in nicht verwaltetem COM-basiertem Code getätigt haben und nicht migrieren möchten, können Sie dennoch mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Webdienste direkt in Ihren vorhandenen Code integrieren. Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.  
  
> [!NOTE]
>  Der Dienstmoniker verwendet einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kommunikationschannel für die gesamte Kommunikation. Die Sicherheits- und Identitätsmechanismen für diesen Channel unterscheiden sich von den Mechanismen in COM- und DCOM-Standardproxys. Da der Dienstmoniker darüber hinaus einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kommunikationschannel verwendet, beträgt die Standardtimeoutdauer für alle Aufrufe eine Minute.  
  
 Der Dienstmoniker wird mit der `GetObject`-Funktion dazu verwendet, dem nicht verwalteten Entwickler einen stark typisierten, COM-spezifischen Ansatz zum Aufrufen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Webdiensten zur Verfügung zu stellen. Dies erfordert eine lokale, für COM sichtbare Definition des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Webdienstvertrags und der zu verwendenden Bindung. Ebenso wie andere [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients muss der Dienstmoniker einen typisierten Kanal für den Dienst erstellen, obwohl diese Kanalerstellung für den COM-Programmierer transparent beim ersten Methodenaufruf erfolgt.  
  
 Bei der Verwendung des Monikers geben Anwendungen ebenso wie andere [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients die Adresse, die Bindung und den Vertrag für die Kommunikation mit einem Dienst an. Der Vertrag kann mithilfe der folgenden Methoden spezifiziert werden:  
  
-   Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.  
  
-   WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.  
  
-   MEX-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX (Metadata Exchange)-Endpunkt abgerufen.  
  
## <a name="parameters-supported-by-the-service-moniker"></a>Vom Dienstmoniker unterstützte Parameter  
 In der folgenden Tabelle werden die Parameter aufgeführt, die vom Dienstmoniker unterstützt werden.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`address`|URL-Adresse des Diensts.|  
|`binding`|Bindungsabschnittsname für die Anwendungskonfiguration.|  
|`bindingConfiguration`|Benannte Bindungsinstanz innerhalb des benannten Bindungsabschnitts.|  
|`contract`|Schnittstellenbezeichner (Interface identifier, IID), der den Dienstvertrag oder den Vertragsnamen (von MEX) darstellt.|  
|`wsdl`|WSDL-Dokument, das eine alternative Form der Vertragsdefinition enthält.|  
|`spnIdentity`|SPN (Server Principal Name)-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.|  
|`upnIdentity`|UPN (User Principal Name)-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.|  
|`dnsIdentity`|DNS-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.|  
|`mexAddress`|URL-Adresse des MEX-Endpunkts (Metadata Exchange) des Diensts.|  
|`mexBinding`|Bindungsabschnittsname für die Anwendungskonfiguration zur Verbindung mit dem MEX-Endpunkt.|  
|`mexBindingConfiguration`|Benannte Bindungsinstanz innerhalb des benannten Bindungsabschnitts zur Verbindung mit dem MEX-Endpunkt.|  
|`bindingNamespace`|Namespace des Bindungsabschnittsnamens für den abgerufenen MEX.|  
|`contractNamespace`|Namespace des Vertrags für den abgerufenen MEX.|  
|`mexSpnIdentity`|SPN (Server Principal Name)-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.|  
|`mexUpnIdentity`|UPN (User Principal Name)-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.|  
|`mexDnsIdentity`|DNS-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.|  
|`serializer`|Geben Sie entweder die Verwendung des "XML"- oder des "datacontract"-Serialisierungsprogramms an.|  
  
> [!NOTE]
>  Auch bei Verwendung mit vollständig COM-basierten Clients erfordert der Dienstmoniker, dass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und .NET Framework 2.0 auf dem Clientcomputer installiert sind. Außerdem müssen Clientanwendungen, die den Dienstmoniker verwenden, die entsprechende Version der .NET Framework-Laufzeit laden. Bei Verwendung des Monikers innerhalb von Office-Anwendungen ist möglicherweise eine Konfigurationsdatei erforderlich, um sicherzustellen, dass die richtige Framework-Version geladen ist. In Excel muss beispielsweise der folgende Text in einer Datei mit dem Namen Excel.exe.config in dasselbe Verzeichnis abgelegt werden wie die Excel.exe-Datei:  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: registrieren und konfigurieren ein Dienstmonikers](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
