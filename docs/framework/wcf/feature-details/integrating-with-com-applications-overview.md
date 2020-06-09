---
title: Übersicht über die Integration von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c283e7cbc4cb4b8bc37dd1313480410df93a93bf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596824"
---
# <a name="integrating-with-com-applications-overview"></a>Übersicht über die Integration von COM-Anwendungen

Windows Communication Foundation (WCF) stellt dem Entwickler von verwaltetem Code eine umfangreiche Umgebung zum Erstellen verbundener Anwendungen zur Verfügung. Wenn Sie jedoch beträchtliche Investitionen in nicht verwalteten COM-basierten Code haben und nicht migrieren möchten, können Sie WCF-Webdienste mit dem WCF-Dienstmoniker weiterhin direkt in Ihren vorhandenen Code integrieren. Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.

> [!NOTE]
> Der Dienstmoniker verwendet einen WCF-Kommunikationskanal für die gesamte Kommunikation. Die Sicherheits- und Identitätsmechanismen für diesen Channel unterscheiden sich von den Mechanismen in COM- und DCOM-Standardproxys. Da der Dienstmoniker außerdem einen WCF-Kommunikationskanal verwendet, beträgt der Standard Timeout Zeitraum eine Minute für alle Aufrufe.

Der Dienstmoniker wird mit der- `GetObject` Funktion verwendet, um dem nicht verwalteten Entwickler einen stark typisierten, com-spezifischen Ansatz zum Aufrufen von WCF-Webdiensten zur Verfügung zu stellen. Hierfür ist eine lokale, com-sichtbare Definition des WCF-Webdienst Vertrags und die zu verwendende Bindung erforderlich. Wie andere WCF-Clients muss der Dienstmoniker einen typisierten Kanal für den Dienst erstellen, obwohl diese Kanal Erstellung für den com-Programmierer beim ersten Methodenaufruf transparent erfolgt.

Gemeinsam mit anderen WCF-Clients geben Anwendungen bei der Verwendung des Monikers die Adresse, die Bindung und den Vertrag für die Kommunikation mit einem Dienst an. Der Vertrag kann mithilfe der folgenden Methoden spezifiziert werden:

- Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.

- WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.

- MEX-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX (Metadata Exchange)-Endpunkt abgerufen.

## <a name="parameters-supported-by-the-service-moniker"></a>Vom Dienstmoniker unterstützte Parameter

In der folgenden Tabelle werden die Parameter aufgeführt, die vom Dienstmoniker unterstützt werden.

|Parameter|BESCHREIBUNG|
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
> Selbst bei Verwendung mit vollständig com-basierten Clients muss der Dienstmoniker WCF und die unterstützende .NET Framework 2,0 auf dem Client Computer installieren. Außerdem müssen Clientanwendungen, die den Dienstmoniker verwenden, die entsprechende Version der .NET Framework-Laufzeit laden. Bei Verwendung des Monikers innerhalb von Office-Anwendungen ist möglicherweise eine Konfigurationsdatei erforderlich, um sicherzustellen, dass die richtige Framework-Version geladen ist. In Excel muss beispielsweise der folgende Text in einer Datei mit dem Namen Excel.exe.config in dasselbe Verzeichnis abgelegt werden wie die Excel.exe-Datei:
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers](how-to-register-and-configure-a-service-moniker.md)
