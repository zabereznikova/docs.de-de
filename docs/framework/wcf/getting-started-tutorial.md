---
title: 'Tutorial: Einstieg in Windows Communication Foundation Anwendungen'
description: Diese Tutorials enthalten eine Einführung in das Erstellen von WCF-Anwendungen.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238235"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Einstieg in Windows Communication Foundation Anwendungen

In der folgenden Reihe von Tutorials werden die Programmierfunktionen Windows Communication Foundation (WCF) vorgestellt. Wenn Sie diese Tutorials in der richtigen Reihenfolge durcharbeiten, erhalten Sie ein Einführ Endes Verständnis der zum Erstellen von WCF-Anwendungen erforderlichen Schritte. Wenn Sie fertig sind, verfügen Sie über einen laufenden WCF-Dienst und einen WCF-Client, der den Dienst aufruft.

In diesem Tutorial wird davon ausgegangen, dass Sie Visual Studio als Entwicklungsumgebung verwenden. Wenn Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die Visual Studio-spezifischen Anweisungen.

Beispiel-WCF-Anwendungen, die Sie herunterladen und ausführen können, finden Sie unter [Windows Communication Foundation Samples](samples/index.md). Eine Einführung in die Beispiele finden Sie unter " [Getting Started Sample](samples/getting-started-sample.md)".

Ausführlichere Informationen zum Erstellen von Diensten und Clients finden Sie unter [grundlegende WCF-Programmierung](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>WCF-Tutorials

In den ersten drei Tutorials wird beschrieben, wie Sie einen WCF-Dienstvertrag definieren, ihn implementieren und hosten. Der von Ihnen erstellte Dienst wird in einer Konsolenanwendung selbst gehostet. Sie können Dienste auch unter Microsoft Internetinformationsdienste (IIS) hosten. Weitere Informationen finden Sie unter Vorgehens [Weise: Hosten eines WCF-Diensts in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Obwohl Sie Code verwenden, um den Dienst im Tutorial zu konfigurieren, können Sie auch [Dienste innerhalb einer Konfigurationsdatei konfigurieren](configuring-services-using-configuration-files.md).

- [Tutorial: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md)

    Sie erstellen einen WCF-Vertrag mit einer benutzerdefinierten Schnittstelle. Dieser Vertrag definiert die Funktionalität, die der Dienst verfügbar macht.

- [Tutorial: Implementieren eines Dienstvertrags](how-to-implement-a-wcf-contract.md)

    Nachdem Sie einen Vertrag definiert haben, müssen Sie ihn mit einer Dienstklasse implementieren.

- [Tutorial: Hosten und Ausführen eines grundlegenden Diensts](how-to-host-and-run-a-basic-wcf-service.md)

    Konfigurieren Sie einen Endpunkt für den Dienst, und Hosten Sie den Dienst in einer Konsolenanwendung. Damit ein Dienst aktiv wird, müssen Sie ihn konfigurieren und innerhalb einer Laufzeitumgebung hosten. Diese Laufzeitumgebung erstellt den Dienst und steuert seinen Kontext und seine Lebensdauer.

In den nächsten beiden Tutorials wird beschrieben, wie eine Client Anwendung erstellt, konfiguriert und verwendet wird, um die vom Dienst verfügbar gemachten Vorgänge aufzurufen. Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert. Visual Studio automatisiert den Prozess des Zugriffs auf diese Metadaten und verwendet diese, um die Client Anwendung für den Dienst zu erstellen. Wenn Sie nicht Visual Studio verwenden möchten, können Sie stattdessen das [Service Model Metadata Utility-Tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden.

- [Tutorial: Erstellen eines Clients](how-to-create-a-wcf-client.md)

    Rufen Sie Metadaten zum Erstellen eines WCF-Client Proxys aus einem WCF-Dienst ab. Sie rufen Metadaten mithilfe von Visual Studio ab, um einen Dienst Verweis hinzuzufügen, oder Sie können das Service Model Metadata Utility-Tool verwenden. Sie geben den Endpunkt an, der vom Client für den Zugriff auf den Dienst verwendet wird.

- [Tutorial: Verwenden eines Clients](how-to-use-a-wcf-client.md)

    Verwenden Sie den WCF-Client Proxy, um die Dienst Vorgänge aufzurufen.

## <a name="reference"></a>Referenz

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Siehe auch

- [Konzeptionelle Übersicht](conceptual-overview.md)
- [Leitfaden zur Dokumentation](guide-to-the-documentation.md)
- [Was ist Windows Communication Foundation](whats-wcf.md)
- [WCF-Funktionsdetails](feature-details/index.md)
- [Grundlegender Programmier Lebenszyklus](basic-programming-lifecycle.md)
- [Clients werden aufgebaut](building-clients.md)
- [Einfache WCF-Programmierung](basic-wcf-programming.md)
- [Vorgehensweise: Erstellen eines Duplex Vertrags](feature-details/how-to-create-a-duplex-contract.md)
- [Vorgehensweise: Zugreifen auf Dienste mit einem Duplex Vertrag](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](using-bindings-to-configure-services-and-clients.md)
- [Beispiel "Getting Started"](samples/getting-started-sample.md)
- [Windows Communication Foundation Beispiele](samples/index.md)
- [Selbst gehostete Dienste](samples/self-host.md)
