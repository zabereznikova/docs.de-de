---
title: Benutzerdefinierte Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 062aba26227fedeea3e5f462ebf5d55cf0cba56c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539996"
---
# <a name="custom-bindings"></a>Benutzerdefinierte Bindungen

Verwenden Sie die <xref:System.ServiceModel.Channels.CustomBinding>-Klasse, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt. Alle Bindungen werden anhand einer geordneten Menge von Bindungselementen erstellt. Benutzerdefinierte Bindungen können alleine aus systemeigenen Bindungselementen erstellt werden oder auch benutzerspezifische Bindungselemente umfassen. So können Sie mithilfe von benutzerdefinierten Bindungselementen beispielsweise die Verwendung neuer Transporte oder Encoder an einem Dienstendpunkt aktivieren. Funktionierende Beispiele finden Sie unter Beispiele für [benutzerdefinierte Bindungen](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)). Weitere Informationen finden Sie unter [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).

## <a name="construction-of-a-custom-binding"></a>Aufbau einer benutzerdefinierten Bindung

Eine benutzerdefinierte Bindung wird unter Verwendung des <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A>-Konstruktors aus einer Sammlung von Bindungselementen erstellt, die in einer spezifischen Reihenfolge „gestapelt“ sind:

- Am Anfang steht eine optionale <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>-Klasse, die den Transaktionsfluss ermöglicht.

- Darauf folgt eine optionale <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>-Klasse, die eine Sitzung und Sortiermechanismen wie in der WS-ReliableMessaging-Spezifikation definiert bereitstellt. Eine Sitzung kann SOAP- und Transportvermittler überqueren.

- Anschließend folgt eine <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse, die Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.

- Hierauf folgt eine optionale <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>-Klasse, die eine Duplexkommunikation mit einem Transportprotokoll ermöglicht, das selbst keine Duplexkommunikation unterstützt, z. B. HTTP.

- Danach folgt eine optionale <xref:System.ServiceModel.Channels.OneWayBindingElement>-Klasse, die eine unidirektionale Kommunikation bereitstellt.

- Dann folgt ein optionales Streamsicherheitsbindungselement, das einem der folgenden Elemente entsprechen kann.

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement. Sie können Ihren eigenen Nachrichtenencoder oder eine von drei Nachrichten codierenden Bindungen verwenden:

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

Am Ende befindet sich ein erforderliches Transportelement. Sie können Ihren eigenen Transport oder eines der folgenden Transport Bindungs Elemente verwenden, Windows Communication Foundation (WCF) Folgendes bietet:

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.

|Ebene|Tastatur|Erforderlich|
|-----------|-------------|--------------|
|Transaktionen|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|Nein|
|Zuverlässigkeit|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|Nein|
|Sicherheit|<xref:System.ServiceModel.Channels.SecurityBindingElement>|Nein|
|Codierung|Text, binär, Message Transmission Optimization Mechanism (MTOM), benutzerdefiniert|Ja|
|Transport|TCP, HTTP, HTTPS, benannte Pipes (Named Pipes, auch als IPC bekannt), Peer-to-Peer (P2P), Message Queuing (auch als MSMQ bekannt), benutzerdefiniert|Ja|

Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.

## <a name="see-also"></a>Siehe auch

- [Übersicht über die Endpunkterstellung](../endpoint-creation-overview.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../using-bindings-to-configure-services-and-clients.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
- [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [Benutzerdefinierte Bindung](../samples/custom-binding.md)
