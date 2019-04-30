---
title: 'Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen'
description: In diesen Tutorials enthält eine Einführung zum Erstellen von WCF-Anwendungen.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: d4613edefeb8db2c0d1e11e925f8ac41329efb0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929542"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen
Die folgende Reihe von Tutorials führen Sie auf der Windows Communication Foundation (WCF) Programmierung. Durcharbeiten dieser Tutorials, in der Reihenfolge erhalten Sie einen einleitenden Überblick über die erforderlichen Schritte zum Erstellen von WCF-Anwendungen. Wenn Sie fertig sind, müssen Sie einen ausgeführten WCF-Dienst und ein WCF-Client, der den Dienst aufruft. 

Dieses Tutorial setzt voraus, dass Sie Visual Studio als Entwicklungsumgebung verwenden. Wenn Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die Visual Studio-spezifische Anweisungen. 

Beispiel WCF-Anwendungen, die Sie herunterladen und ausführen können, finden Sie unter [Windows Communication Foundation-Beispiele](samples/index.md). Eine Einführung in den Beispielen, finden Sie unter [Beispiel für erste Schritte](samples/getting-started-sample.md).

Ausführlichere Informationen zum Erstellen von Diensten und Clients finden Sie unter [einfache WCF-Programmierung](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>WCF-Lernprogramme

Die ersten drei Tutorials wird beschrieben, wie einen WCF-Dienstvertrag definiert, wie er implementiert und wie zu hosten. Der Dienst, den Sie erstellen, ist innerhalb einer Konsolenanwendung selbst gehostet. Sie können auch Dienste unter Microsoft Internet Information Services (IIS) hosten. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten ein WCF-Diensts in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Obwohl Sie Code verwenden, um den Dienst in diesem Tutorial konfigurieren, können Sie auch [Dienste innerhalb einer Konfigurationsdatei konfigurieren](configuring-services-using-configuration-files.md). 

- [Tutorial: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md)

    Sie erstellen einen WCF-Vertrags mit einer benutzerdefinierten Benutzeroberfläche. Dieser Vertrag definiert die Funktionalität, die der Dienst verfügbar macht.

- [Tutorial: Implementieren eines Dienstvertrags](how-to-implement-a-wcf-contract.md)

    Nachdem Sie einen Vertrag zu definieren, müssen Sie es mit einer Dienstklasse implementieren.

- [Tutorial: Hosten und Ausführen eines grundlegenden Diensts](how-to-host-and-run-a-basic-wcf-service.md)

    Konfigurieren Sie einen Endpunkt für den Dienst, und hosten Sie des Diensts in einer Konsolenanwendung. Für einen Dienst aktiviert wird müssen Sie konfigurieren und hosten Sie es in einer Laufzeitumgebung. Diese Runtime-Umgebung den Dienst erstellt und steuert seinen Kontext sowie seine Lebensdauer.

Die nächsten beiden Tutorials beschrieben, wie zum Erstellen und konfigurieren und Verwenden einer Clientanwendung zum Aufrufen des Diensts durch die Vorgänge verfügbar macht. Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert. Visual Studio automatisiert den Zugriff auf diese Metadaten und wird verwendet, um die Clientanwendung für den Dienst zu erstellen. Wenn Sie nicht Visual Studio verwenden möchten, können Sie mithilfe der [ServiceModel Metadata Utility-Tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) stattdessen.

- [Tutorial: Erstellen Sie einen client](how-to-create-a-wcf-client.md)

    Abrufen von Metadaten für einen WCF-Clientproxy von einem WCF-Dienst erstellen. Rufen Sie Metadaten mithilfe von Visual Studio zum Hinzufügen eines Dienstverweises aus, oder Sie können das ServiceModel Metadata Utility-Tool verwenden. Sie geben Sie den Endpunkt, den der Client verwendet, um den Dienst zuzugreifen.

- [Tutorial: Verwenden Sie einen client](how-to-use-a-wcf-client.md)

    Verwenden Sie den WCF-Clientproxy, um Dienstvorgänge aufzurufen.

## <a name="reference"></a>Referenz

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Siehe auch

- [Konzeptionelle Übersicht](conceptual-overview.md)
- [Führen Sie in der Dokumentation](guide-to-the-documentation.md)
- [Was ist Windows Communication Foundation](whats-wcf.md)
- [Details zur WCF-Funktion](feature-details/index.md)
- [Grundlegende Programmierung Lebenszyklus](basic-programming-lifecycle.md)
- [Erstellen von clients](building-clients.md)
- [Grundlegende WCF-Programmierung](basic-wcf-programming.md)
- [Vorgehensweise: Erstellen eines duplexvertrags](feature-details/how-to-create-a-duplex-contract.md)
- [Vorgehensweise: Von Access Services mit einem Duplexvertrag](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Vorgehensweise: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Verwenden von Bindungen, um Dienste und Clients konfigurieren](using-bindings-to-configure-services-and-clients.md)
- [Beispiel für erste Schritte](samples/getting-started-sample.md)
- [Windows Communication Foundation-Beispiele](samples/index.md)
- [Selbst gehostete Dienste](samples/self-host.md)
