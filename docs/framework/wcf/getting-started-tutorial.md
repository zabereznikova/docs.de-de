---
title: Erste Schritte Tutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: b7ba25795dd69e5bd978c77928f9b9797f4d4e19
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200883"
---
# <a name="getting-started-tutorial"></a>Lernprogramm 'Erste Schritte'
In diesem Abschnitt enthaltenen Themen sollen Sie schnelle Offenlegung auf der Windows Communication Foundation (WCF) Programmierung erteilen. Die Liste am Ende dieses Themas gibt Aufschluss über die Reihenfolge, in der die Aufgaben ausgeführt werden müssen. Für dieses Tutorial vermittelt Ihnen Grundkenntnisse zu der die erforderlichen Schritte zum WCF-Dienst und Client-Anwendungen erstellen. Ein Dienst macht einen oder mehrere Endpunkte verfügbar, von denen jeder wiederum einen oder mehrere Dienstvorgänge zur Verfügung stellt. Die *Endpunkt* eines Diensts gibt eine Adresse, in dem der Dienst gefunden werden kann, eine Bindung, die Informationen, die beschreibt enthält, wie ein Client kommunizieren muss, mit dem Dienst und einen Vertrag, der die Funktionen definiert sind, vom Dienst für seine Clients bereitgestellt werden.

 Nachdem Sie die Themenfolge dieses Lernprogramms durchgearbeitet haben, verfügen Sie über einen funktionierenden Dienst und über einen Client, der den Dienst aufrufen kann. Die ersten drei Themen beschreiben, wie ein Dienstvertrag definiert und implementiert und wie der Dienst gehostet wird. Der erstellte Dienst ist innerhalb einer Konsolenanwendung selbst gehostet. Dienste können auch unter IIS (Internetinformationsdienste) gehostet werden. Weitere Informationen hierzu finden Sie unter [Vorgehensweise: Hosten ein WCF-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). Der Dienst wird im Code konfiguriert. Dienste können jedoch auch in einer Konfigurationsdatei konfiguriert werden. Weitere Informationen zur Verwendung einer Konfigurationsdatei finden Sie unter [Konfigurieren von Diensten mithilfe von Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).

 In den nächsten drei Themen wird beschrieben, wie ein Clientproxy erstellt, die Clientanwendung konfiguriert und der Clientproxy verwendet wird, um einen Dienstvorgang aufzurufen, der vom Dienst verfügbar gemacht wird. Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert. Visual Studio 2012 automatisiert den Zugriff auf diese Metadaten und zum Erstellen und konfigurieren Sie die Clientanwendung für den Dienst verwendet. Wenn Sie nicht Visual Studio 2012 verwenden, können Sie mithilfe der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellen und konfigurieren die Clientanwendung für den Dienst.

Die Themen in diesem Abschnitt wird davon ausgegangen, dass Sie Visual Studio als Entwicklungsumgebung verwenden. Wenn Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die Visual Studio-spezifische Anweisungen.

Für die Beispielanwendungen, die auf die Festplatte heruntergeladen werden können und auszuführen, finden Sie unter den Themen in [Windows Communication Foundation (WCF)-Beispiele](./samples/index.md). In diesem Thema finden Sie insbesondere die [Einstieg](../../../docs/framework/wcf/samples/getting-started-sample.md).

Ausführlichere Informationen zum Erstellen von Diensten und Clients finden Sie unter [Basis-WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md).

## <a name="in-this-section"></a>In diesem Abschnitt
 [Vorgehensweise: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)

 Beschreibt die Erstellung ein WCF-Dienstvertrags mithilfe einer benutzerdefinierten Schnittstelle. Der Vertrag definiert die Funktionalität, die vom Dienst verfügbar gemacht wird.

 [Vorgehensweise: Implementieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

 Beschreibt das Implementieren eines Dienstvertrags. Sobald ein Vertrag definiert ist, muss es mit einer Dienstklasse implementiert werden.

 [Vorgehensweise: Hosten und Ausführen eines grundlegenden Diensts](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)

 Beschreibt, wie im Code ein Endpunkt für den Dienst konfiguriert wird und wie der Dienst innerhalb einer Konsolenanwendung gehostet wird. Zur Aktivierung muss der Dienst in einer Laufzeitumgebung konfiguriert und gehostet werden. Diese Umgebung erstellt den Dienst, und steuert seinen Kontext sowie seine Lebensdauer.

 [Vorgehensweise: Erstellen Sie einen Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

 Beschreibt, wie zum Abrufen von Metadaten verwendet, um einen WCF-Clientproxy mit einem WCF-Dienst zu erstellen. Dieser Prozess verwendet die Funktionalität Hinzufügen eines Dienstverweises in Visual Studio.

 [Vorgehensweise: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

 Beschreibt, wie ein WCF-Client konfiguriert wird. Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen.

 [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

 Beschreibt, wie den WCF-Clientproxy verwendet wird, um Dienstvorgänge aufzurufen.

## <a name="reference"></a>Referenz

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="related-sections"></a>Verwandte Abschnitte

- [Windows Communication Foundation (WCF)-Beispiele](./samples/index.md)
- [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)

## <a name="see-also"></a>Siehe auch

- [Konzeptionelle Übersicht](../../../docs/framework/wcf/conceptual-overview.md)
- [Anleitung zur Dokumentation](../../../docs/framework/wcf/guide-to-the-documentation.md)
- [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)
- [Details zur WCF-Funktion](../../../docs/framework/wcf/feature-details/index.md)
