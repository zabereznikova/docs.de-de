---
title: 'Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen'
description: Diese Tutorials bieten eine Einführung zum Erstellen von WCF-Anwendungen.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184121"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen
In der folgenden Reihe von Tutorials werden Sie mit der Programmiererfahrung von Windows Communication Foundation (WCF) vorgestellt. Wenn Sie diese Tutorials in der Reihenfolge durchlaufen, erhalten Sie ein einführendes Verständnis der Schritte, die zum Erstellen von WCF-Anwendungen erforderlich sind. Nach Abschluss des Abschlusses verfügen Sie über einen ausgeführten WCF-Dienst und einen WCF-Client, der den Dienst aufruft.

Im Tutorial wird davon ausgegangen, dass Sie Visual Studio als Entwicklungsumgebung verwenden. Wenn Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die Visual Studio-spezifischen Anweisungen.

Beispielen für WCF-Anwendungen, die Sie herunterladen und ausführen können, finden Sie unter [Windows Communication Foundation-Beispiele](samples/index.md). Eine Einführung in die Beispiele finden Sie unter [Erste Schritte .](samples/getting-started-sample.md)

Ausführlichere Informationen zum Erstellen von Diensten und Clients finden Sie unter [Grundlegende WCF-Programmierung](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>WCF-Tutorials

In den ersten drei Lernprogrammen wird beschrieben, wie ein WCF-Dienstvertrag definiert, wie er implementiert und wie er hosten wird. Der von Ihnen erstellte Dienst wird in einer Konsolenanwendung selbst gehostet. Sie können Dienste auch unter Microsoft Internet Information Services (IIS) hosten. Weitere Informationen finden Sie unter [Gewusst wie: Hosten eines WCF-Dienstes in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Obwohl Sie Code zum Konfigurieren des Dienstes im Tutorial verwenden, können Sie auch [Dienste innerhalb einer Konfigurationsdatei konfigurieren.](configuring-services-using-configuration-files.md)

- [Tutorial: Definieren eines Servicevertrags](how-to-define-a-wcf-service-contract.md)

    Sie erstellen einen WCF-Vertrag mit einer benutzerdefinierten Schnittstelle. Dieser Vertrag definiert die Funktionalität, die der Dienst verfügbar macht.

- [Tutorial: Implementieren eines Servicevertrags](how-to-implement-a-wcf-contract.md)

    Nachdem Sie einen Vertrag definiert haben, müssen Sie ihn mit einer Serviceklasse implementieren.

- [Tutorial: Hosten und Ausführen eines Basisdienstes](how-to-host-and-run-a-basic-wcf-service.md)

    Konfigurieren Sie einen Endpunkt für den Dienst, und hosten Sie den Dienst in einer Konsolenanwendung. Damit ein Dienst aktiv wird, müssen Sie ihn konfigurieren und in einer Laufzeitumgebung hosten. Diese Laufzeitumgebung erstellt den Dienst und steuert seinen Kontext und seine Lebensdauer.

In den nächsten beiden Lernprogrammen wird beschrieben, wie Sie eine Clientanwendung erstellen, konfigurieren und verwenden, um die Vorgänge aufzurufen, die der Dienst verfügbar macht. Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert. Visual Studio automatisiert den Zugriff auf diese Metadaten und verwendet sie, um die Clientanwendung für den Dienst zu erstellen. Wenn Sie Visual Studio nicht verwenden möchten, können Sie stattdessen das [ServiceModel Metadata Utility-Tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden.

- [Tutorial: Erstellen eines Clients](how-to-create-a-wcf-client.md)

    Abrufen von Metadaten zum Erstellen eines WCF-Clientproxys aus einem WCF-Dienst. Sie rufen Metadaten ab, indem Sie Visual Studio verwenden, um einen Dienstverweis hinzuzufügen, oder Sie können das ServiceModel-Metadatendienstprogramm verwenden. Sie geben den Endpunkt an, den der Client für den Zugriff auf den Dienst verwendet.

- [Tutorial: Verwenden eines Clients](how-to-use-a-wcf-client.md)

    Verwenden Sie den WCF-Clientproxy, um die Dienstvorgänge aufzurufen.

## <a name="reference"></a>Verweis

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Weitere Informationen

- [Konzeptionelle Übersicht](conceptual-overview.md)
- [Leitfaden zur Dokumentation](guide-to-the-documentation.md)
- [Was ist Windows Communication Foundation](whats-wcf.md)
- [WCF-Featuredetails](feature-details/index.md)
- [Grundlegender Programmierlebenszyklus](basic-programming-lifecycle.md)
- [Baukunden](building-clients.md)
- [Grundlegende WCF-Programmierung](basic-wcf-programming.md)
- [Gewusst wie: Erstellen eines Duplexvertrags](feature-details/how-to-create-a-duplex-contract.md)
- [Gewusst wie: Zugriff auf Dienste mit Duplexvertrag](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [ServiceModel-Metadaten-Dienstprogramm (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](using-bindings-to-configure-services-and-clients.md)
- [Erste Schritte Beispiel](samples/getting-started-sample.md)
- [Windows Communication Foundation-Beispiele](samples/index.md)
- [Selbst gehostete Dienste](samples/self-host.md)
