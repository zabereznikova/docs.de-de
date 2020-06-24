---
title: 'Endpunkte: Adressen, Bindungen und Verträge'
description: Erfahren Sie, wie die gesamte Kommunikation mit einem WCF-Dienst über die Dienst Endpunkte erfolgt, die Clients Zugriff auf die vom Dienst angebotenen Funktionen bieten.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247311"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Endpunkte: Adressen, Bindungen und Verträge

Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Dienstanbieter. Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die von einem WCF-Dienst angeboten wird.

Jeder Endpunkt verfügt über vier Eigenschaften:

- Eine Adresse, die angibt, wo der Endpunkt zu finden ist.

- Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.

- Ein Vertrag, der die verfügbaren Vorgänge identifiziert.

- Eine Gruppe von Verhaltensweisen, die lokale Implementierungsdetails des Endpunkts angeben.

In diesem Thema wird diese Endpunkt Struktur behandelt und erläutert, wie Sie im WCF-Objektmodell dargestellt wird.

## <a name="the-structure-of-an-endpoint"></a>Die Struktur eines Endpunkts

Jeder Endpunkt besteht aus Folgendem:

- Adresse: Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern des Diensts den Standort des Diensts mit. Sie wird im WCF-Objektmodell durch die- <xref:System.ServiceModel.EndpointAddress> Klasse dargestellt. Eine <xref:System.ServiceModel.EndpointAddress>-Klasse enthält:

  - Eine <xref:System.ServiceModel.EndpointAddress.Uri%2A>-Eigenschaft, die die Adresse des Diensts darstellt.

  - Eine <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft, die die Sicherheits-ID des Diensts und eine Auflistung optionaler Nachrichtenheader darstellt. Die optionalen Nachrichtenheader werden verwendet, um zusätzliche und ausführlichere Adressinformationen bereitzustellen, um den Endpunkt zu identifizieren oder damit zu interagieren.

  Weitere Informationen finden Sie unter [Angeben einer Endpunkt Adresse](../specifying-an-endpoint-address.md).

- Bindung: Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet. Dies schließt Folgendes ein:

  - Das Transportprotokoll, das verwendet werden soll (z.&#160;B. TCP oder HTTP).

  - Die Codierung, die für die Nachrichten verwendet werden soll (z.&#160;B. Text oder binär).

  - Die erforderlichen Sicherheitsanforderungen (z.&#160;B. SSL- oder SOAP-Nachrichtensicherheit).

  Weitere Informationen finden Sie unter [Übersicht über WCF-Bindungen](../bindings-overview.md). Eine Bindung wird im WCF-Objektmodell durch die abstrakte Basisklasse dargestellt <xref:System.ServiceModel.Channels.Binding> . Für die meisten Szenarien können Benutzer eine der vom System bereitgestellten Bindungen verwenden. Weitere Informationen finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md).

- Verträge: Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt. Ein Vertrag gibt Folgendes an:

  - Welche Vorgänge von einem Client aufgerufen werden können.

  - Die Form der Nachricht.

  - Der Typ der Eingabeparameter oder Daten, die zum Aufrufen des Vorgangs erforderlich sind.

  - Den Typ der Verarbeitung oder der Antwortnachricht, den der Client erwarten kann.

  Weitere Informationen zum Definieren eines Vertrags finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md).

- Verhaltensweisen: Sie können das lokale Verhalten des Dienstendpunkts mithilfe von Endpunktverhaltensweisen anpassen. Endpunkt Verhaltensweisen erreichen dies durch die Teilnahme an der Einrichtung einer WCF-Laufzeit. Ein Beispiel für ein Endpunktverhalten ist die <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>-Eigenschaft, mit der Sie eine andere Listeningadresse als die SOAP- oder die WSDL-Adresse (WSDL = Web Services Description Language) angeben können. Weitere Informationen finden Sie unter [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).

## <a name="defining-endpoints"></a>Definieren von Endpunkten

Sie können den Endpunkt für einen Dienst entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angeben. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Dienst Endpunkts in der Konfiguration](how-to-create-a-service-endpoint-in-configuration.md) und Gewusst [wie: Erstellen eines Dienst Endpunkts im Code](how-to-create-a-service-endpoint-in-code.md).

## <a name="in-this-section"></a>In diesem Abschnitt

In diesem Abschnitt wird der Zweck von Bindungen, Endpunkten und Adressen erläutert. Darüber hinaus wird gezeigt, wie Sie eine Bindung und einen Endpunkt konfigurieren und wie Sie das `ClientVia`-Verhalten und die `ListenUri`-Eigenschaft verwenden.

[Setzt](endpoint-addresses.md)\
Beschreibt, wie Endpunkte in WCF adressiert werden.

[Land](bindings.md)\
Beschreibt, wie mit Bindungen Transport, Codierung und Protokolldetails angegeben werden, die für die Kommunikation zwischen Clients und Diensten erforderlich sind.

[Verträge](contracts.md)\
Beschreibt, wie Verträge die Methoden eines Diensts definieren.

[Vorgehensweise: Erstellen eines Dienst Endpunkts in der Konfiguration](how-to-create-a-service-endpoint-in-configuration.md)\
Beschreibt, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.

[Vorgehensweise: Erstellen eines Dienst Endpunkts im Code](how-to-create-a-service-endpoint-in-code.md)\
Beschreibt, wie Sie einen Dienstendpunkt im Code erstellen.

[Gewusst wie: Verwenden von Svcutil.exe zum Überprüfen von kompiliertem Dienst Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)\
Beschreibt, wie Fehler in Dienst Implementierungen und Konfigurationen erkannt werden, ohne dass der Dienst mit dem Service [Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)gehostet wird.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von Diensten](../configuring-services.md)
- [Erweitern von Bindungen](../extending/extending-bindings.md)
