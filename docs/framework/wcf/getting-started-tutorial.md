---
title: Erste Schritte Tutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 64d9fc09d56c417c2226d030ef6f5ee7204c4eb6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806018"
---
# <a name="getting-started-tutorial"></a>Lernprogramm 'Erste Schritte'
In diesem Abschnitt enthaltenen Themen sollen Sie schnelle Offenlegung an der Windows Communication Foundation (WCF) Programmierung geben. Die Liste am Ende dieses Themas gibt Aufschluss über die Reihenfolge, in der die Aufgaben ausgeführt werden müssen. Dieses Lernprogramm bietet Ihnen Grundkenntnisse zu der die erforderlichen Schritte zum Erstellen von WCF-Dienst und Client Anwendungen. Ein Dienst macht einen oder mehrere Endpunkte verfügbar, von denen jeder wiederum einen oder mehrere Dienstvorgänge zur Verfügung stellt. Die *Endpunkt* eines Diensts gibt die Adresse, auf dem der Dienst gefunden werden kann, eine Bindung, die Informationen, die beschreibt enthält, wie ein Client kommunizieren muss, mit dem Dienst und einen Vertrag, der die Funktionen definiert sind, vom Dienst für seine Clients bereitgestellt werden.  
  
 Nachdem Sie die Themenfolge dieses Lernprogramms durchgearbeitet haben, verfügen Sie über einen funktionierenden Dienst und über einen Client, der den Dienst aufrufen kann. Die ersten drei Themen beschreiben, wie ein Dienstvertrag definiert und implementiert und wie der Dienst gehostet wird. Der erstellte Dienst ist innerhalb einer Konsolenanwendung selbst gehostet. Dienste können auch unter IIS (Internetinformationsdienste) gehostet werden. Weitere Informationen hierzu finden Sie unter [wie: Hosten eines WCF-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). Der Dienst wird im Code konfiguriert. Dienste können jedoch auch in einer Konfigurationsdatei konfiguriert werden. Weitere Informationen zum Verwenden einer Konfigurationsdatei finden Sie unter [Konfigurieren von Diensten mithilfe von Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 In den nächsten drei Themen wird beschrieben, wie ein Clientproxy erstellt, die Clientanwendung konfiguriert und der Clientproxy verwendet wird, um einen Dienstvorgang aufzurufen, der vom Dienst verfügbar gemacht wird. Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] automatisiert den Zugriff auf diese Metadaten und verwendet sie, um die Clientanwendung für den Dienst zu erstellen und zu konfigurieren. Wenn Sie nicht arbeiten [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], können Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen und konfigurieren die Clientanwendung für den Dienst.  
  
 In allen Themen in diesem Abschnitt wird davon ausgegangen, dass Sie Visual Studio 2011 als Entwicklungsumgebung verwenden. Wenn Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die entsprechenden Visual Studio-Anweisungen.  
  
> [!NOTE]
>  Ausgeführtes Betriebssystem [!INCLUDE[wv](../../../includes/wv-md.md)] oder höheren Versionen des Betriebssystems Windows müssen Sie Visual Studio starten, indem wechseln Sie im Startmenü mit der rechten Maustaste auf Visual Studio 2011 und auswählen **als Administrator ausführen**. Visual Studio 2011 immer als Administrator starten, erstellen eine Verknüpfung, klicken Sie mit der mit der rechten Maustaste auf die Verknüpfung, wählen Sie Eigenschaften aus, wählen Sie, die **Kompatibilität** Registerkarte, und überprüfen Sie die **führen dieses Programm als Administrator** Kontrollkästchen. Wenn Sie Visual Studio&#160;2011 über diese Verknüpfung starten, wird es immer im Administratormodus ausgeführt.  
  
 Für Beispielanwendungen, die auf die Festplatte heruntergeladen werden können und ausgeführt wurde, finden Sie unter den Themen in [Windows Communication Foundation-Beispiele](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91). In diesem Thema, siehe, insbesondere die [Einstieg](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Weitere ausführliche Informationen zum Erstellen von Diensten und Clients, finden Sie unter [grundlegende WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Beschreibt das Erstellen eines WCF-Dienstvertrags mithilfe einer benutzerdefinierten Schnittstelle. Der Vertrag definiert die Funktionalität, die vom Dienst verfügbar gemacht wird.  
  
 [Vorgehensweise: Implementieren eines WCF-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Beschreibt das Implementieren eines Dienstvertrags. Sobald ein Vertrag definiert ist, müssen Sie ihn mit einer Dienstklasse implementieren.  
  
 [Vorgehensweise: Hosten und Ausführen eines grundlegenden Diensts](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Beschreibt, wie im Code ein Endpunkt für den Dienst konfiguriert wird und wie der Dienst innerhalb einer Konsolenanwendung gehostet wird. Zur Aktivierung muss der Dienst in einer Laufzeitumgebung konfiguriert und gehostet werden. Diese Umgebung erstellt den Dienst, und steuert seinen Kontext sowie seine Lebensdauer.  
  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Beschreibt, wie zum Abrufen von Metadaten verwendet, um einen WCF-Clientproxy mit einem WCF-Dienst zu erstellen. Dieser Prozess verwendet die Funktion "Dienstverweis hinzufügen" in Visual Studio 2011.  
  
 [Vorgehensweise: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Beschreibt, wie ein WCF-Client konfiguriert wird. Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen.  
  
 [Vorgehensweise: Verwenden eines Clients](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Beschreibt, wie die WCF-Clientproxy verwenden, um Dienstvorgänge aufzurufen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Windows Communication Foundation-Beispiele](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzeptionelle Übersicht](../../../docs/framework/wcf/conceptual-overview.md)  
 [Anleitung zur Dokumentation](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Details zur WCF-Funktion](../../../docs/framework/wcf/feature-details/index.md)
