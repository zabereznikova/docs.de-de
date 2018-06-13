---
title: Übersicht über die Integration von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c789d4a52da9b2785fb5919a674bf19f23d23509
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493395"
---
# <a name="integrating-with-com-applications-overview"></a>Übersicht über die Integration von COM-Anwendungen
Windows Communication Foundation (WCF) enthält, die Entwickler von verwaltetem Code eine reichhaltige Umgebung zum Erstellen von verbundenen Anwendungen. Jedoch, wenn Sie eine erhebliche Investition in nicht verwaltetem Code mit COM-basierten haben und nicht migrieren möchten, können Sie weiterhin WCF-Webdiensten direkt in den vorhandenen Code integrieren mit den WCF-Dienstmoniker. Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.  
  
> [!NOTE]
>  Der Dienstmoniker verwendet einen WCF-Kommunikationskanal für die gesamte Kommunikation. Die Sicherheits- und Identitätsmechanismen für diesen Channel unterscheiden sich von den Mechanismen in COM- und DCOM-Standardproxys. Außerdem, da der Dienstmoniker einen Kommunikationskanal zwischen WCF das Standardtimeout verwendet beträgt für alle Aufrufe eine Minute.  
  
 Der Dienstmoniker wird verwendet, mit der `GetObject` der Funktion den nicht verwalteten Entwickler einen stark typisierten, COM-spezifischen Ansatz zum Aufrufen von WCF-Webdiensten. Dies erfordert eine lokale, COM sichtbare Definition der WCF-Web-Dienstvertrag und die Bindung, die verwendet werden soll. Wie andere WCF-Clients muss der Dienstmoniker einen typisierten Kanal für den Dienst erstellen, obwohl diese kanalerstellung für den COM-Programmierer beim ersten Methodenaufruf transparent erfolgt.  
  
 Geben Sie auch in zahlreichen anderen WCF-Clients, bei Verwendung des Monikers Anwendungen, die Adresse, Bindung und Vertrag für die Kommunikation mit einem Dienst. Der Vertrag kann mithilfe der folgenden Methoden spezifiziert werden:  
  
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
>  Selbst bei Verwendung mit vollständig COM-basierten Clients erfordert der Dienstmoniker WCF und unterstützende .NET Framework 2.0 auf dem Clientcomputer installiert sein. Außerdem müssen Clientanwendungen, die den Dienstmoniker verwenden, die entsprechende Version der .NET Framework-Laufzeit laden. Bei Verwendung des Monikers innerhalb von Office-Anwendungen ist möglicherweise eine Konfigurationsdatei erforderlich, um sicherzustellen, dass die richtige Framework-Version geladen ist. In Excel muss beispielsweise der folgende Text in einer Datei mit dem Namen Excel.exe.config in dasselbe Verzeichnis abgelegt werden wie die Excel.exe-Datei:  
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
 [Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
